---
layout: post
title: Automated Provisioning Part 3
categories: [vrealize, chef, automation]
tags: [automation]
fullview: true
comments: true
---

The Orchestrator workflow that was kicked off in the previous post will install and bootstrap the chef client.  The validator certificate is included in the Windows template so it is available for each client install.  The script we use is as follows:


I use two main cookbooks to configure the web and sql servers.

The web cookbook will install all the roles and features required to run IIS and sets up the Inetpub folder structure.  The sql cookbook will install SQL.  The configuration.ini is build using attributes.  Each cookbook is in a seperate role which contains a base cookbook which every server gets and dns cookbook which sets up the dns for each of the api's being deployed.  The Octopus tenticle is installed by Chef Client on each of the servers.

Octopus then downloads the code and configures IIS.
