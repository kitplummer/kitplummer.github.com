---
layout: post
title: From OSGi back to Grails...
---

One of the interesting architecture/design issues we’ve had to overcome
in building our [OSGi](http://felix.apache.org) -powered
[Grails](http://www.grails.org) web-app was how to get from OSGi bundles
to GORM’s domain models. At the risks associated with toying in
relatively uncharted waters we avoided the Hibernate/GORM combo in the
OSGI side. Initially we just made basic SQL queries to perform CRUD
actions on the tables. Obviously this isn’t remotely optimal (db
changes, no hibernate events, etc.). So the next logical step was to
have the OSGi bundles communication straight to the already built REST
interfaces for the web-app. This gives us fairly good decoupling, and
the ability to work against the builtin validations and events provided
by GORM.

Knowing that we needed a basic HTTP layer from within the OSGi bundles I
needed a library (surprisingly there’s really know REST-abstraction lib
either). Found that the lastest and greatest [Http
Components](http://hc.apache.org/) project at Apache builds out OSGi
bundles. They are still beta or SNAPSHOT material but I’m pretty
confident the functionality I need is solid.

<filter:jzfilter lang="java">  
…  
import org.apache.http.NameValuePair;  
import org.apache.http.client.entity.UrlEncodedFormEntity;  
import org.apache.http.message.BasicNameValuePair;  
import org.apache.http.protocol.HTTP;  
import org.apache.http.HttpEntity;  
import org.apache.http.impl.client.DefaultHttpClient;  
import org.apache.http.client.methods.HttpPut;  
import org.apache.http.client.methods.HttpPost;  
import org.apache.http.client.HttpClient;  
import org.apache.http.StatusLine;  
import org.apache.http.HttpResponse;  
import org.apache.http.conn.HttpHostConnectException;  
…

public Boolean writeView(String subViewName, String data, String viewId,
String restInf) {

try {  
HttpClient client = new DefaultHttpClient();

// restInf is the Grails app URL provided into this class, view the
resource.  
HttpPost post = new HttpPost(restInf + “/view/” + viewId);

// load up the data into the parameters  
List <NameValuePair> nvps = new ArrayList <NameValuePair>();  
nvps.add(new BasicNameValuePair(“data”, data));  
post.setEntity(new UrlEncodedFormEntity(nvps, HTTP.UTF\_8));

// execute - the REST request  
HttpResponse response = client.execute(post);  
if (response.getStatusLine().getStatusCode() == 200) {  
return true;  
} else {  
return false;  
}  
} catch (HttpHostConnectException e) {  
return false;  
} catch (Exception e) {  
e.printStackTrace();  
return false;  
}

}  
</filter:jzfilter>

Not too bad. Have similar operations for Update and Delete too. Be
forewarned we did have trouble using HttpPut (PUT) methods to perform
Update actions. One of the application servers (OAS) we must deploy too
simply couldn’t handle it - and had to revert to using POST.

Now we can use the Hibernate events to perform model functionality from
both the external and internal interfaces. Much better. Getting the OSGi
bundles to build with HTTPComponents was a simple add to our Maven
pom.xml and setting the requisite “import” for the each bundle.

<filter:jzfilter lang="xml">  
<dependency>  
<groupId>org.apache.httpcomponents</groupId>  
<artifactId>httpclient</artifactId>  
<version>4.0-beta1</version>  
</dependency>  
<dependency>  
<groupId>org.apache.httpcomponents</groupId>  
<artifactId>httpcore-osgi</artifactId>  
<version>4.0-beta3</version>  
</dependency>  
</filter:jzfilter>
