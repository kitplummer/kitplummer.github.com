---
layout: post
title: AWS EC2 on Leopard...
---

I was having a helluva time getting Amazon’s
[ec2-api-tools](http://developer.amazonwebservices.com/connect/entry.jspa?externalID=351&categoryID=88)
to run on my MB with Leopard. Ultimately the trick was:

    <code>
    $ export JAVA_HOME=/System/Library/Frameworks/JavaVM.framework/Versions/CurrentJDK/Home
    $ cp jsr173_api-1.0.jar $JAVA_HOME/lib/endorsed
    </code>

FWIW, I already had a few “other” libs in the endorsed directory:

    <code>
    -rw-r--r--  1 root  wheel   63018 Oct 16 17:26 activation-1.1.jar
    -rw-r--r--  1 root  wheel   73738 Oct  5 10:17 jaxb-api-2.0.jar
    -rw-r--r--  1 root  wheel  784198 Oct 16 17:25 jaxb-impl-2.0.3.jar
    -rw-r--r--  1 root  wheel   49672 Dec 18 19:23 jsr173_api-1.0.jar
    </code>

Now, everything is working, as expected. I was kinda surprised to find
that no one else had this problemo…weird.

Thanks to my “esteemed” colleague Brian O’Neill for dropping this dandy
[gem](http://amazon-ec2.rubyforge.org/) on me this morning. Perdy cool.
