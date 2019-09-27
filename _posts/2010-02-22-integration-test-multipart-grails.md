---
layout: post
title: Multi-part Form Integration Test in Grails
tags: open grails
---

{{ page.title }}
================

Thanks to [this](http://markmail.org/message/zcpepup3udecoldw) post I
was able to figure it out. Wasn’t simple, but have the integration test
working. I did notice that Grails automatically creates a
“org.springframework.web.multipart.support.DefaultMultipartHttpServletRequest”
and not just a
“org.springframework.web.multipart.MultipartHttpServletRequest” request.
But, all is well.

So, hopefully this helps someone else too.

Here’s my test:

<script src="http://gist.github.com/311284.js?file=multipart-integration-grails.groovy">
</script>
