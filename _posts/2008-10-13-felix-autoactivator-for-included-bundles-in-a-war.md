---
layout: post
title: Felix AutoActivator for Included Bundles in a WAR...
---

I had to do a bit of Java magic to get to the “right” classpath when
trying to use the AutoActivator.AUTO\_START\_PROP to load external OSGi
bundles. It took a bit, and I finally found the solution hidden in the
depths of the Felix mailing list.

I’m actually starting Felix from inside Grail’s BootStrap.groovy file,
so here’s the snip of code:

<filter:jzfilter lang="groovy">  
def configMap = new StringMap(false)

configMap.put(FelixConstants.EMBEDDED\_EXECUTION\_PROP, “true”)

configMap.put(Constants.FRAMEWORK\_SYSTEMPACKAGES,  
“org.osgi.util.tracker; version=1.3.2,” +  
“org.apache.felix.shell; version=1.0.2,” +  
“javax.swing.border;,” +  
“javax.swing.event;,” +  
“javax.swing.table;,” +  
“javax.swing.tree;,” +  
“javax.naming;,” +  
“javax.naming.spi;,” +  
“javax.net;,” +  
“javax.net.ssl;,” +  
“javax.sql;,” +  
“javax.swing;,” +  
“org.osgi.framework; version=1.4.0,” +  
“org.osgi.service.packageadmin; version=1.2.0,” +  
“org.osgi.service.startlevel; version=1.1.0,” +  
“org.osgi.service.url; version=1.0.0,”);

def bundles =  
this.getClass().getClassLoader().getResource(“WAR-INF/lib/com.springsource.org.hsqldb-1.8.0.9.jar”).toString()
+ " " +  
this.getClass().getClassLoader().getResource(“WAR-INF/lib/org.apache.felix.shell-1.0.2.jar”).toString()
+ " " +  
this.getClass().getClassLoader().getResource(“WAR-INF/lib/org.apache.felix.shell.remote-1.0.2.jar”).toString()

configMap.put(AutoActivator.AUTO\_START\_PROP + “.1”, bundles)  
</filter:jzfilter>
