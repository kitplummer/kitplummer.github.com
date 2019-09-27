---
layout: post
title: Community-Based Development...
---

<div>
<h2>

Introduction

</h2>

It is widely known that the Open Source community uses a different
approach (Bazaar) to software engineering – over traditional,
proprietary environments (Cathedral)\[1\]. However, there are many
opportunities to apply Open Source practices to internal software
engineering efforts, where the software product is consumed by another
internal organization. Integrating these practices is not trivial…though
in most cases it is just a matter of utilizing a few new, or different
tools. In some cases, there may need to be a cultural shift, or simply a
new awareness.  
<br><br>  
In order to avoid any confusion in the distinction between true Open
Source development, where there is a “public” interface and
intra-organizational development I’d like to call the generic practices
found in the Open Source world Community-Based Development (CBD).  
<br><br>  
CBD serves the environment where one team is developing software that
has consumption potential. Notice I didn’t say reuse, which is a
chokepoint for many engineers. Consumption, in this case, means library,
API, or interface implementation – not source code copy n’ paste. The
“customer” is another developer, or engineering project. CBD is about
optimizing this kind of relationship, especially where the customer is
proactive in the development of the source product.  
<br><br>

<h2>

Background

</h2>

There are a few key functions, or tools used in this provider-customer
relationship – many of which are clearly defined in Producing Open
Source Software \[2\].  
<br><br>  
Here’s the quick (not all inclusive) breakdown:

<ul>
<li>

Mailing lists - Dev, Announcements, Users, Builds, etc.

<li>

RSS feeds - Tie into mailing lists, issue tracking

<li>

Issue Tracking

<li>

SCM

<li>

Wiki

<li>

Search (projects and code)

<li>

Admin Management (Users, Roles, Project setup, etc.)

<li>

Web Site

</ul>

On the Open Source side of the fence these tools are usually
consolidated, and provided from a single user-interface (website). In
many cases, projects are homed into a parent structure, provided by a
“hosting” service. There are a few examples such as
SourceForge.net\[3\], or Java.net\[4\] which front-end many projects.
The software platforms that provide these infrastructures are available
for commercial application in both proprietary and Open Source form. In
addition, there project infrastructure suites such as Redmine.org\[5\]
that are designed specifically for internal/team-centric software
engineering collaboration.  
<br><br>

<h2>

Integration

</h2>

There are a few “tough” questions that arise when considering CBD,
especially as applied to internal relationships. The first, and probably
most obvious, is how to integrate CBD with existing processes and
methodologies. Existing processes can usually accommodate CBD with
little pain. CBD is a complimentary environment, and can integrate
seamlessly in to any methodology (waterfall, spiral, agile). Where
things get really complicated is in the tooling. Most development
environments are already using individual tools to perform specific
functions (e.g. issue tracking, project management). How CBD is applied
where existing tools are entrenched – should not be a replacement
effort. Although, there may be some duplication – the idea is to expose
the integrated collaboration tool suite to both the product developer(s)
and the customer, or product consumer/integrator. Continuous integration
environments shouldn’t be affected – as the source code repository is
independent from the project suite.  
<br><br>

<h2>

Discovery

</h2>

Keep in mind that the developer-developer relationship requires that the
consumer have the ability to search/discovery the internal software
product. Just having code in a repository with an associated issue
tracking system doesn’t lend itself as available for consummation. This
is why the SourceForge (centralized collection of projects) is prevalent
in the Open Source community. Having a centralized source of CBD
projects leads to the potential for consummation because they can be
discovered.  
<br><br>

<h2>

Governance

</h2>

In order to maintain a “community” project there is a requisite
membership ideal. Usually, the project owner plays the leadership role,
whereas the consumer plays member (active or passive). CBD requires
members be given roles to control access to data, ability to commit
changes, as well as general project management activities. Again, having
the consolidated project environment ensures that user administration is
consistent across all projects, as well as providing a potential for
parent-sub project relationships. The consolidated suite of tools also
ensures that the project owner can control the roles and privileges
without implicating administrative personnel.  
<br><br>

<h2>

Community

</h2>

The idea of a community-based approach to software engineering is based
on the principle that the consumer is integral in the development, much
in the same way as Agile Methodologies manage the customer relationship.
The consumer’s activity may be as simple as reviewing/editing
documentation or providing input via issues and bug reports. Or, it can
be as proactive as the consumer writing code and submitting it to the
project. Regardless, the objective is to maintain the codebase for the
continued and growing consumption without duplicating anything across
the organization. Internal to an organization, there may be boundaries
specified by contract, external customers, or functional hierarchies
that make it difficult for software to be reused. The notion of CBD can
help overcome this by removing the demarcations and continuously
improving the “wheel” without starting over.  
<br><br>

<h2>

References

</h2>
<ul>
<li>

\[1\] The Cathedral and the Bazaar, by Eric S. Raymond
(<a href="http://www.catb.org/~esr/writings/cathedral-bazaar/cathedral-bazaar/">http://www.catb.org/\~esr/writings/cathedral-bazaar/cathedral-bazaar/</a>)

<li>

\[2\] Producing Open Source Software by Karl Fogel
(<a href="http://producingoss.com">http://producingoss.com</a>)

<li>

\[3\] SourceForge
(<a href="http://www.sourceforge.net">http://www.sourceforge.net</a>)

<li>

\[4\] Java.net (<a href="http://www.java.net">http://www.java.net</a>)

<li>

\[5\] Redmine
(<a href="http://www.redmine.org">http://www.redmine.org</a>)

</ul>
</div>
