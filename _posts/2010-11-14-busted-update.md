---
layout: post
title: Busted Update...Open Development/Government.
tags: open, tucson
categories:
- tucson
---

{{ page.title }}
================

Hey OpTucs.

Just wanted to give props to Lucas Taylor for making a small, and
needed, updated to the Busted feed service.

<https://github.com/kitplummer/Busted/pull/1>

The details of the fix aren’t really all that important or exciting
here. What is really cool, and worth sharing, is the actual process of
collaboration.

This is how I think it went down. At the last Open Tucson shindig, which
Lucas and I attended, we discussed a few ideas about how the group can
participate in the opening of Tucson’s data sources and promote greater
transparency within the local governments. One of the solutions, that
actually started during our Great American Hackathon last year, was the
retrofitting of the SunTran bus feed into a more usable and accessible
format - and has been dubbed Busted (by me). Busted has since turned
into an opportunity for further development as a data source for a few
different ideas revolving around local-business advertising and mobile
applications.

Because Busted is open source Lucas was not only able to access the data
feed, but also the code that actually does the raw data transformations.
Lucas found a small issue with one of the bus feeds. (In my opinion this
is where things get really cool.) Because the code is hosted at
<http://github.com>, a social coding and collaboration site, Lucas was
able to “clone” my repository into his own personal environment and make
the required changes. The key here is that he was able to do so without
me even knowing - or having to gain permission to my repository. Lucas
then made the fixes.

Obviously it doesn’t end here. Because most open source development is
done, well, in the ope n - there are typical geographic distribution
challenges to overcome. The software development world, long familiar
with this requirement, has create various tools to help work with
distributed code. One of those, and the backbone of Github, is called
git. Git is distributed version control system (DVCS) that provides the
“cloning” capability that allowed Lucas to copy my repository and work
within his own environment. Git also provides an apparatus for
distributing the changes that Lucas made, back to me, or anyone else for
that matter (who might have also cloned my repository). Git calls this
transaction a “pull request” and Github makes this dead simple by
generating the request and sending it to me as message (email too). For
me to incorporate Lucas’ fix it took a couple steps and voila, we’re now
in sync and my repository has been updated and Busted has been made
better. It took a single additional step for me to send the new Busted
to t he “cloud” and affect the “live” feed.

All of this sounds really complex, or really easy - but let me assure it
is closer to the latter. The value of data transparency is only the
starting point for improving our governments. Transparency is required
all the way out to the organizations and communities who are creating
solutions. Open Tucson and all of the other “Government 2.0”
organizations need more of this type of collaboration. Thanks to Lucas
for the opportunity to highlight the coolness of “openness”.

Kit

\[This is a copy of a post made to the Open Tucson Google group’s
discussion forum, but it doesn’t have public access yet.\]
