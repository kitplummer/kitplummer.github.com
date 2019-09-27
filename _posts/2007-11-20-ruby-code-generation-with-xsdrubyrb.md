---
layout: post
title: Ruby - Code Generation with xsd2ruby.rb...
---

I actually blogged in great detail about this in a previous
blog/life…which I can’t find anywhere. I couldn’t even find it with
<http://web.archive.org>, imagine that.

Code generation is something that I grew to really appreciate on a
previous project where we decided that every potential message would
exist as an XSD (or compilation of XSDs). I’ve been toying/working with
Ruby a bit lately, and once again have the opportunity to do some code
generation. First, let me state that I’m not a fan of SOAP. I’m learning
to really appreciate the simplicity of REST/HTTP - so even though I’m
pointing at the [soap4r](http://dev.ctor.org) project I wish this stood
by itself.

Once again, I have a few schemas that represent messages - messages I’d
really like to be able to pump out as HTTP POSTs to a REST servlet with
ruby.

So, here it is: xsd2ruby.rb. This little ruby in the rough is part of
the [soap4r](http://dev.ctor.org/soap4r) package. If you “install” via
the gem you get a executable in /usr/local/bin which you can run from
where ever. This is how it works:

    <code>
    Usage: /usr/local/bin/xsd2ruby.rb --xsd xsd_location [options]
      xsd_location: filename or URL

    Example:
      /usr/local/bin/xsd2ruby.rb --xsd myapp.xsd --classdef foo

    Options:
      --xsd xsd_location
      --classdef [filenameprefix]
      --mapping_registry
      --mapper
      --module_path [Module::Path::Name]
      --force
      --quiet
    </code>

Once you have the classes, you can build objects in a breeze, and
marshall ’em:

    <code>
    @xmlString = XSD::Mapping.obj2xml(@message, nil, nil)
    </code>

Way cool stuff! Hopefully, this blog sticks around a bit longer than my
last attempt…
