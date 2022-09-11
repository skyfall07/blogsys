---
title: "Upgrade Workspace One 21.08"
header:
  overlay_color: "#9e7a7a"
categories:
  - Post Formats
tags:
  - WorkspaceOne
  - VMware
toc: true
---

Tips and troubleshooting before and after upgrading Workspace One

# Reading:

Okay, you want to upgrade your Workspace One cluster(s) to the version 21.08 ? Here some tips and troubleshooting you can apply beofre and after doing the upgrade

First you should read carefully the official documentation of the upgrade [here](https://docs.vmware.com/en/VMware-Workspace-ONE-Access/21.08/ws1_access_upgade.doc/GUID-9D3BCE4A-6711-4CCD-AF7E-7EA23DB66697.html) 
And meet all the prerequistes before performing the upgrade.

# Prerequisites:

## Disk Sizing:

Before upgrade, be careful to have enought space disk on the sd4 partition (you can find a tutorial here : ), it must be at least 10GB free

## DBOwner

You must then verify that the account is use to connect to the external database has the dbowner rights, you can verify that by connecting to the server where the database is stored.

If the database is stored on Windows, you can easely doing it either with SQL requests, or with MYSQL Management on your Windows Server

## Network Card

Before upgrading your node, verify that your node have VMNEXT3 Network Card. If it's not the case, be carefull to change it. Shutdown the node, delete the exisiting network card, and add a new one. Of course, verify when you reboot the appliance that the network settings are good, and that the health dashboard is green before to proceed with the whole cluster.

# The Upgrade

If you have a Cluster, only during the upgrade of the first node your cluster will be down, you can except around 1 hour (in my case less) of downtime. To be carefull, the best would be to take 1h30 windows, in the case you want to roll back during the upgrade

On the first node :

Log as root account on your appliance :

```markdown
[root@WSP1:~] cd /test/test/test/upgradeoffline
```
It will prompt you yo choose a new password.

# Troubleshooting

In the official document, VMware already cover fews cases that can happen during or after the upgrade, first take a look to the official document of the upgrade, and if you can of course, open a ticket to the VMware support if you can access it, if not let's hope your case already exist.

## Network Issues

you can have few differents Network Issues during your upgrade. The first thing you need to identify is first if you are using VApp or not. If not, I would recommend to use Vapp for your VMware cluster if it's a possibility (if you are with On-premises deployment), here you can find the properties you need to configure :


