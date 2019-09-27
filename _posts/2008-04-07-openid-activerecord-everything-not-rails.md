---
layout: post
title: OpenID, ActiveRecord, Everything Not Rails...
---

Wow. I started to get a “real” sense for the state of Rails and the
surrounding Ruby-based frameworks on Friday morning. You know what they
say about making promises…

Needless to say I don’t have a working geo-client. I did chase about
every possible rabbit. There were some promising options including Merb
with a generic session captured in DataMapper. Ironically the simplest
solution is the Ramaze one. Way unfortunate that they aren’t pushing the
OpenID capability. I think if I had the time, I’d debug their
OpenID-mongrel problem. But, I still believe we should get the
geo-client over to Rails for the sake of continuity across our
code/project-base.

The real irony here is that everyone has seemed to go the custom OpenID
solution based on the openid-ruby gem. Not necessarily surprised just
wondering way the people that put effort into a plugin for Rail
1.x/OpenID 1.x are putting the same effort in to maintaining them for
Rail and OpenID version 2s. Strange. This is one of the problems that I
think the Java world with its more Darwinian approach to projects. But,
due to the Rails defacto documentation being blog posts the old (weak)
stuff seems to live off for ever…and not get maintained in the same way
as Java-ish projects - it really is self-centered. I supposed this is
somewhat due to RubyForge, and the general lack of a true “foundation”
to house Ruby projects ala Apache or Eclipse. I wonder why that is. No,
not really I know why. It is because of shops like 37Signals…not
“getting” the greater good part of Open Source. Don’t get me wrong I’m
not necessarily fault them - just saying that they are definitely partly
responsible for the state of things Ruby and Ruby on Rails.

ActiveRecord is a terd. I appreciate most of what it brings to the
table…but, I’m really struggling with it - and any intuitive
understanding. I’ll take the blame for most of it - not all of it. For
example, why does this work:

    <code>
    @openid = UserOpenids.find(:first, :conditions => ["user_id = ?", @user.id])
    </code>

And not this:

    <code>
    @openid = UserOpenids.find_by_user_id(:first, @user.id)
    </code>

It took me at least 4 hours to figure this effer out…and I still don’t
understand.
