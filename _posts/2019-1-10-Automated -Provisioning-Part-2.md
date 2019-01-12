---
layout: post
title: Automated Provisioning Part 2
categories: [vrealize, orchestrator, automation]
tags: [automation]
fullview: true
comments: true
---

vRealize Automation was unable to complete the builds on its own so I needed to be able to run Orchestrator workflows as well.  The way to trigger orchestrator workflows from vRealize Automation is through the use of the Event Broker servers, or Subscriptions.

Subscriptions live under the Administration tab and then Events.  Select Subscriptions.

To create a new subscription, click on New

Click All of the 

* Data - Lifecycle State - MachineProvision
- Data - Lifecycle  - PRE
- Enter manually in the field "Data~Machine~Properties~SomeProperty"
    + Must use the ~ between each level

Click Next and select the workflow to execute

Click Next and select Blocking or not.  You cannot adjust this setting one saved.  Blocking means that the vRealize Automation build will halt until it receives a response from Orchestrator or hits the time out.

Click Save and then Publish.
