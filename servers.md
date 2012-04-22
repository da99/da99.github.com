---
layout: page
title: "Setup Servers and Deploying Apps"
description: ""
---
{% include JB/setup %}

Right now I manage less than 5 work/personal servers. I use:

* Custom Ruby code. (I gave up on Chef-solo and Sprinkle.)
* Ohai gem with the [linux/platform plugin](https://github.com/opscode/ohai/blob/master/lib/ohai/plugins/linux/platform.rb).
* capistrano
* [Bootstrap for RBENV](https://github.com/da99/boot_ups/tree/master/straps)

I wrote the server info in my ~/.ssh/config. I wrote [Chef-Solo-Nodes](https://github.com/da99/Chef_Solo_Nodes)
to integrate my nodes with Capistrano, but it turned out I did not need it. The ssh/config file is enough.

I avoid use of [knife-solo](https://github.com/matschaffer/knife-solo)
and instead use Capistrano.  In the future, I would most likely use
Chef-Solo and related tools instead of Capistrano.  Until then,
it is easier to use Capistrano to send commands to Chef nodes.

I use Capistrano to execute a shell script (bootstrap) that installs
RBENV and Chef-Solo.  Then I can send other commands to run the
Chef recipes.

In order to share data between servers, I commit the data to 
a git repo and do a "git push". I use a private repo on 
BitBucket because they offer free private repos.  You do not have to 
do this if you use Chef Server.

