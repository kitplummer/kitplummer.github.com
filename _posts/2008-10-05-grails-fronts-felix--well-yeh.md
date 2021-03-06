---
layout: post
title: Grails Fronts Felix?  Well, yeh...
---

Basically, there’s not much to it. Ha! There’s a lot too it, and I’ll
probably miss many nuggest in my report here. But, hopefully interested
parties will feel free to comment.

\[Preface NOTE: I am not embedding Grails into OSGi, as a bundle. I’m
making Grails the “host” for the OSGi framework. I simply think this is
easier…and fits my architecture.\]

I realized really quickly that I was going to need to use the
‘grails-maven-plugin’ to wrap the ant commands to get better management
of the libraries I need from the Grails side. Plus, my Ant skills are
lacking. Once I had Grails working via maven I was able to add a few
dependencies to the build - automatically adding the libs to the lib/ on
‘mvn install’. I added the Felix stuff to the newly created Grail’s
project pom.xml config:

    <code>
    ...
    <dependency>
      <groupId>org.apache.felix</groupId>
      <artifactId>org.apache.felix.shell</artifactId>
      <version>1.0.2</version>
    </dependency>
    <dependency>
      <groupId>org.apache.felix</groupId>
     <artifactId>org.apache.felix.main</artifactId>
     <version>1.2.1</version>
    </dependency>
    ...
    </code>

I’ve put all of the Felix magic into the Bootstrap.groovy file:

    <code>
    import org.osgi.framework.*
    import org.apache.felix.framework.Felix
    import org.apache.felix.framework.util.FelixConstants
    import org.apache.felix.framework.cache.BundleCache
    import org.apache.felix.framework.util.StringMap
    import org.apache.felix.main.AutoActivator
    import java.util.Map
    import org.springframework.context.ApplicationContext 
    import com.accenture.netcds.*
    import org.codehaus.groovy.grails.web.servlet.GrailsApplicationAttributes

    class BootStrap {
        def cachedir = File.createTempFile("felix.tmp", null);

        def init = { 
            servletContext ->

            cachedir.delete()

            def configMap = new StringMap(false)

            configMap.put(FelixConstants.EMBEDDED_EXECUTION_PROP, "true")

            configMap.put(Constants.FRAMEWORK_SYSTEMPACKAGES,
                "org.osgi.util.tracker; version=1.3.2," +
                "org.apache.felix.shell; version=1.0.2," +
                "org.osgi.framework; version=1.4.0," +
                "org.osgi.service.packageadmin; version=1.2.0," +
                "org.osgi.service.startlevel; version=1.1.0," +
                "org.osgi.service.url; version=1.0.0," +
                "org.osgi.service.shell; version=1.0.2");

                configMap.put(AutoActivator.AUTO_START_PROP + ".1",
                "file:lib/org.apache.felix.shell-1.0.2.jar " +
                "file:lib/org.apache.felix.shell.remote-1.0.2.jar")

                configMap.put(FelixConstants.LOG_LEVEL_PROP, "1")

                configMap.put(BundleCache.CACHE_PROFILE_DIR_PROP, cachedir.getAbsolutePath())
                // Create list to hold custom framework activators.
                List list = new ArrayList()
                // Add activator to process auto-start/install properties.
                list.add(new AutoActivator(configMap))
                // Add our own activator.
                //list.add(this);

                try
                {
                    // Now create an instance of the framework.
                    Felix felix = new Felix(configMap, list)
                    felix.start();
                    log.debug("Started Felix!")

                    ApplicationContext ctx = servletContext.getAttribute(GrailsApplicationAttributes.APPLICATION_CONTEXT)

                    InterpreterServiceInf service = (InterpreterServiceInf) ctx.getBean("interpreterService")
                    if (service.setBundleContext(felix.getBundleContext())) {
                        log.debug("GRAILS SERVICE LOADED: " + service.getName())
                    }

                }
                catch (Exception ex)
                {
                    System.err.println("Could not create framework: " + ex)
                    ex.printStackTrace()
                    System.exit(-1)
                }
            }
            def destroy = {
                deleteFileOrDir(cachedir);
                System.out.println("Removing BundleCache")
            }


        }
    </code>

The really important part to note here is the ApplicationContext and the
InterpreterServiceInf stuff. This is how the link between my
controller(s) and the OSGi services is made. The InterpreterServiceInf
is a plain Grails Service:

    <code>
    import org.osgi.framework.*

    class InterpreterService implements InterpreterServiceInf {

        boolean transactional = false
        def name = "Interpreter Service"
        def BundleContext context

        def Boolean interpret(String blah) {
            return true
        }

        def Boolean setBundleContext(BundleContext ctx) {
            this.context = ctx
            return true
        }

        def BundleContext getBundleContext() {
            return this.context
        }

        def String getName() {
            return this.name
        }
    }
    </code>

So the Bootstrap loads the BundleContext into the service, which is then
available anywhere within Grails, like a controller:

    <code>
    def save = {
            def resource = new Resource(params)
            if(!resource.hasErrors() && resource.save()) {

                def data = fetcherService.fetch(source)
                def bundleCtx = interpreterService.getBundleContext() 
                def serviceRefs = bundleCtx.getServiceReferences("com.accenture.netcds.dds.interpreter.OsgiInterpreterServiceInf", null)

                // Loop through the list of all InterpreterService(s) register in Felix
                for (serviceRef in serviceRefs) {
                    def viewName = serviceRef.getProperty("view")

                    // For each interpreter will take published view name and send 'er to the ORM.
                    def view = new View()
                    view.name = viewName
                    view.resource = resource
                    view.save()

                    // Get an instance of each interpreter and fire off the data
                    def svc = bundleCtx.getService(serviceRef)

                    bundleCtx.ungetService(serviceRef)
                }

                flash.message = "Resource ${resource.id} created and Interpreters fired!"
                redirect(action:show,id:resource.id)
            }
            else {
                render(view:'create',model:[resource:resource])
            }
        }
    </code>

I’ve “cleaned” this code a bit, so if the logic fails you that’s why.
The basic idea is that a data resource comes into the controller, then
the OSGi framework is queried for all interpreters (the name being
written to a local ReST resource. Lastly, the data is passed to each
one.

Amazingly it actually works. Well at least I think it does. I’ve only
done some very basic functionality discovery here which show the data
passing through the interfaces. I don’t have a good feel for how this
works from a threading/performance perspective. I’m making some
assumptions and diving deeper in the areas where I need to know more.
But, wanted to get this out there…because I surely didn’t find this
information when I started.

Now, to the next question…how do I get the OSGi service to talk to the
HSQLDB database underneath Grails? So, far I’ve just started to scrape
the surface and am running into a JDBC driver issue. More to come for
sure.
