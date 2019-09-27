---
layout: post
title: Vagrant is My New Best Friend 
tags: devops
categories:
- devops
---

{{ page.title }}
================

[Vagrant](http://www.vagrantup.com) is my new best friend. Well, really
it is the latest tool I’m adding to my development toolbox - or I should
say my DevOps toolbox.

Vagrant is a Ruby-based utility for simple interaction with
[VirtualBox](http://www.virtualbox.org) (Oracle’s open source
virtualization product). Rather than posting a tutorial…this is how
simple it is:

    <code>$ gem install vagrant
    $ vagrant box add base http://files.vagrantup.com/lucid32.box
    $ vagrant init
    $ vagrant up
    $ vagrant ssh</code>

Of course, you have to have already installed VirtualBox. But, this gets
you a basic Ubuntu Lucid (32-bit) environment, installed, running and
logged in. How cool is that???

This works great for me, as one of my target environments is CentOS 5.5.
Yep, you guessed it - theres an available CentOS5.5 box available for
downloading/running. I’ve learned the hard way that you have to keep
each environment in its own directory, because the VM settings are
stored in a file called Vagrantfile.

    <code>$ mkdir CentOS5.5 && cd CentOS5.5
    $ vagrant box add centos http://dl.dropbox.com/u/15307300/vagrant-0.7-centos-64-base.box
    $ vagrant init centos
    $ vagrant up
    $ vagrant ssh</code>

It’s also possible to configure the VM using
[Puppet](http://www.puppetlabs.com) - but again my intent isn’t for this
to be a tutorial, so check the Vagrant
[docs](http://vagrantup.com/docs/provisioners/puppet_server.html) if
you’re interested. I do this so I can quickly get Subversion and a few
other tools install really quickly.
