---
layout: post
title: Rails Vs. Merb...Footprint?
---

So, I realize if you are reading this you actually care about Rails and
Merb. Therefore I hope you are not absolutely perturbed at the lack of
quality content here. :)

Out of strange curiosity I decided to see which framework was truly
lighter in “default” form. I simply ran each’s command to create a blank
projects then looked at the “size” of the created directory.

    <code>
    $ rails test
    </code>

The resulting project weighed in at 400KB.

    <code>
    $ merb-gen app test
    </code>

Merb’s project weighs in at 104KB.

Amazing? No, not really. But, now I’m wondering what the size of a
Grails project is…
