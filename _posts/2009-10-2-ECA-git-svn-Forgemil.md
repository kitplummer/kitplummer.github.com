---
layout: post
title: ECA, git-svn, and Forge.mil
---

{{ page.title }}
================

I validated today that it is possible to use
[git-svn](http://www.kernel.org/pub/software/scm/git/docs/git-svn.html)
with [Forge.mil](https://software.forge.mil) and the standard Subversion
client - if you are using an ECA. There probably is a way to trick Git
into finding the non-standard SVN client if you’re using a CAC. I could
probably help if needed.

Good news. Now I can mirror projects easily between
[Github](http://github.com) and Forge.mil. Obviously there’s no real
point here, save for simplifying access to some code. Well, I suppose
there could be some specific configuration that would require the code
to lie in within the Forge.mil firewall - but, then that’s probably up
for a bad “smell” award.

There’s a couple of small tips:

[This blog
post](http://www.viget.com/extend/effectively-using-git-with-subversion/)
talks about using git-svn - which is a big help.

Also, I found that with a little Subversion configuration on the client
side you can eliminate the ECA certificate/password request.

The [SVN docs](http://svnbook.red-bean.com/en/1.0/ch06s04.html) show it
in detail, but here’s the skinny:

In your ‘.svn/subversion/servers’ file under the \[groups\] header ad
this line:

    <code>forgemil = svn.forge.mil</code>

Then, create a new section after the \[global\] section like this:

    <code>[forgemil]
    ssl-client-cert-file = /path/to/your/cert.p12
    ssl-client-cert-password = your certificate password
    </code>

There you go. Then to checkout a Forge.mil repo:

    <code>git-svn clone https://svn.forge.mil/svn/repos/your_repo local_dir</code>

Now you’re off and capable of using git locally. Mucho bueno.
