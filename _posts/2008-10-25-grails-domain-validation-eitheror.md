---
layout: post
title: Grails Domain Validation - Either/Or...
---

Had a interesting need to do validation on two fields and ensure one or
the other had (valid) input.

Here’s what the code looks like:

<filter:jzfilter lang="groovy">  
class Resource {  
String url  
String data

static hasMany = \[views:View\]

static constraints = {  
url(nullable: true, url: true, validator: { val, obj -\>  
if (obj.url  null && obj.data  null) return \[‘url OR data
required.’\]  
})  
data(nullable: true, maxSize:5000, validator: { val, obj -\>  
if (obj.data  null && obj.url  null) return \[‘url OR data
required.’\]  
})

}

String toString() {  
this.id  
}  
}  
</filter:code>

Nothing spectacular…just simple.
