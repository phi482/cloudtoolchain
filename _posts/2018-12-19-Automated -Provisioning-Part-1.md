---
layout: post
title: Automated Provisioning Part 1
categories: [vrealize, chef, automation]
tags: [automation]
fullview: true
comments: true
---

This time last year our organization was in desperate need to quickly spin up a virtual environment as we were developing a new application.  We were already heavily invested in VMware and owned licensing for vRealize Automation.  I told our team I had part of the solution but it would be a total team effort to get this working.  We needed a web server and a SQL server.  It needed to tie into our code deployment tool, Octopus, and several other internal systems.  It also had to stand a lone and not impact the other development servers.

We enlisted a vendor to get stated and we came up with a three tier solution.
* vRealize Automation would be the request portal and create the virtual machines
- Chef would manage the configurations for the 2 Windows servers
- Octopus Delploy would deploy all of the code

The next parts of this series will go into detail for each tier and how they all tie together.
