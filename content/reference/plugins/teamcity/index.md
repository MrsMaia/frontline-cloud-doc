---
title: "Teamcity Plugin"
description: "Learn how to configure the Gatling Enterprise TeamCity plugin and run your simulations."
lead: "Run your Gatling Enterprise simulations from your TeamCity CI."
date: 2021-03-08T12:50:20+00:00
lastmod: 2021-08-05T13:13:30+00:00
weight: 30020
---

## Purpose of this plugin

This plugin allows you to start a Gatling Enterprise simulation directly from your TeamCity platform. This plugin links a TeamCity plan with one and only one Gatling Enterprise simulation.

This plugin doesn't create a new Gatling Enterprise simulation, you have to create it manually before.

## Installation

To download the plugin, you need to get the zip file located at:

```
https://downloads.gatling.io/releases/frontline-teamcity-plugin/{{< var externalPluginsVersion >}}/frontline-teamcity-plugin-{{< var externalPluginsVersion >}}.zip
```

You need to be connected as an administrator of your TeamCity application to install it. Navigate to **Administration**, **Plugins**, **Upload plugin zip**, and choose the downloaded zip file.

{{< img src="upload-plugin.png" alt="Upload plugin" >}}

Once the plugin is uploaded, you need to enable it.

## Configuration

The plugin needs some global configuration. Go **Administration**, then **frontline-teamcity-plugin**.

The **Gatling Enterprise Address** is the address of Gatling Enterprise, please enter: https://cloud.gatling.io.

The [Gatling Enterprise API Token]({{< ref "../../admin/api_tokens" >}}) is needed to authenticate to Gatling Enterprise. The API token needs the All permission.

{{< img src="administration.png" alt="" >}}

## Plan set-up

Add a new build step called **FrontLine Launcher**. Choose in the Simulation list the simulation you want to monitor. You need to configure the global properties of the plugin, and create at least a simulation on Gatling Enterprise to do this step.

{{< img src="configuration.png" alt="Configuration" >}}

### JUnit reporting

You can display the results of the Gatling Enterprise assertions as a JUnit Test.

Add a new build feature called **XML report processing**. Choose **Ant JUnit** as report type, and enter in the **Monitoring rules** input the following line:

`gatlingFrontLineJunitResults/*.xml`

{{< img src="junit.png" alt="JUnit" >}}

## Usage

A new Gatling Enterprise simulation will be started every time the job is run. Check the Console Log to see the advancement of the simulation. If the simulation ran successfully, it will look like the following:

{{< img src="log.png" alt="Console Log" >}}

When the job run is finished, you will be able to see on the **Gatling Enterprise Results** tab, the summary of the Gatling Enterprise simulation.

{{< img src="display-results.png" alt="Display results" >}}
