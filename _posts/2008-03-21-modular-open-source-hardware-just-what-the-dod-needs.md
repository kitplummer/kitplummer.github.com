---
layout: post
title: Modular, Open Source Hardware - Just What the DoD Needs...
---

It seems to me that the there’s still a great void in the tech industry.
FOSS is establishing itself with clout in all sectors including the
Departement of Defense. So, why is Open Source hardware so far behind?
The easy answer is that it isn’t so easy. ;) To play with and contribute
to a hardware design is considerably more complex than with software.
Plus, most organizations see hardware as the value added. It is a shame
really…but, understood.

In my experience as a Defense contractor there is a huge amount of waste
in the redevelopment of computing architectures because of form-factor
or resource constraints. For operational environment reasons, devices
and general electronics are constantly reproduced because access to
design artifacts aren’t available. Granted, general purpose electronics
and processors aren’t as pervasive as the same in the software world.
But, they should be. At minimum the hardware should be designed with
standard connectors and interfaces - so as to be made “modular”.

The guys at [BUG Labs](http://buglabs.net) are doing just this. But,
more importantly they’ve identified the relationship between the
hardware and the software - and even at a higher level. The idea that
hardware can be somewhat generic and integrated at the lowest level,
then integrated at a middle-level via a software development kit to
create any number of high-level applications that take advantage of the
permutation of hardware is really incredible. Really, this is
component-based engineering as it should be.

Here’s a very basic (abstract) use case for how the DoD, or more
specifically, how contractors could take advantage of this BUG
architecture:

Consider an unmanned air frame, and let’s assume that it could
accommodate a modular hardware suite to include sensor A, B, or C;
effector X or Y, and radio R or S. Consider a mission profile of “find,
fix, kill, and verify”. Potentially this could be accommodated by the
right combination of hardware. But, let’s not stop there. One more
consideration…imagine that with the right payloads the mission tasking
could be extended to a 10-hour operational window by distributing the
payloads to multiple airframes (decreasing the payload weight allowing
for the extended flight time).

Let’s walk thru a few steps:

1\. Maintenance crew “installs” the hardware modules on to the vehicles.
Sensor A and C on vehicle 1. Effector X on vehicle 2. Both vehicles are
equipped with radio R. Status lights indicate the correct local
operations and POST passes.

2\. Crew chief connects (wifi or wired) the two vehicles to the OPS
network.

3\. Mission planner sees the vehicles as “available” and begin linking
the assets to mission requirements. By drag-n-drop functions the
planners use the MP suite to create the local software configurations
for each vehicle, then combines the capabilities to meet the “find, fix,
kill and verify” profile as a “cell” capability. Test suites, models and
simulations are run to verify actual system characteristics.

4\. Mission planner generates the appropriate interface control
documentation (ICD) for the cell (as well as security profile) with the
click of a button. The ICD is used to request data from the cell, or
command the cell from remote systems.

5\. Mission planner registers the cell capability via the ICD with
up-chain systems such as C2.

\[In my example, sensor A is used to “find and fix” the target. Effector
X is used to “kill”. Sensor C is used to verify the kill. Radios are
used to communicate air-to-air and air-to-ground.\]

All of the software/operational integration is done automagically.
Obviously hidden in the magic are loads of interface standards,
definitions, and registration/discovery processes. The key is that they
are all available…and mechanisms for completing my scenario all exist.
The BUG Labs is doing is based on open standards and specifications such
as OSGi, Java is already Open. It would seem to make sense to leverage
this capability, expanding it to meet the more advanced needs of a
Defense environment. 80% of the problem has already been solved. The
same scenario could be applied to logistics problems, uniform issue and
load-outs, etc. Net-centricity goes beyond the connectivity…automation
and optimization are ripe for the taking.
