---
layout: post
title: Using Restlet's Jetty Server with JUnit - Integration Testing the ReST Interface...
---

Here’s my test class setup:

    <code>
    @BeforeClass
        public static void setUpServer() throws Exception {
            // Create a new Component.
            component = new Component();
            // Add a new HTTP server listening on port 8182.
            component.getServers().add(Protocol.HTTP, 8182);

            // Attach the sample application.
            component.getDefaultHost().attach(
                    new MyApplication(component.getContext()));

            // Create an application
            Application test = new Application(component.getContext()) {
                @Override
                public Restlet createRoot() {
                    Reference rootUri = LocalReference.createFileReference(new File("./src/test/resources"));
                    return new Directory(getContext(), rootUri);
                }
            };
            component.getClients().add(Protocol.FILE);
            component.getDefaultHost().attach("/test", test);
            // Start the component.
            component.start();
    </code>

So, this takes files in ‘src/test/resources’ and makes them available
through the spun up HTTP server. And, by taking advantage of the JUnit
annotations we can ensure this only happens once, before any of the test
code. Nice, eh? I’ve created a RFE at Restlet.org to provide direct
support for non-absolute file paths, which the LocalReference works
around (nicely).
