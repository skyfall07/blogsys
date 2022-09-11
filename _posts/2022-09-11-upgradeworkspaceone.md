---
title: "Upgrade Workspace One 21.08"
header:
  overlay_color: "#333"
categories:
  - Post Formats
tags:
  - WorkspaceOne
  - VMware
toc: true
---

Okay, you want to upgrade your Workspace One cluster(s) to the version 21.08 ? Here some tips and troubleshooting you can apply beofre and after doing the upgrade

#Reading:

First you should read carefully the official documentation of the upgrade [here](https://docs.vmware.com/en/VMware-Workspace-ONE-Access/21.08/ws1_access_upgade.doc/GUID-9D3BCE4A-6711-4CCD-AF7E-7EA23DB66697.html) 
And meet all the prerequistes before performing the upgrade.


Then directly press Enter, no need to enter root password (hopefully for us in that case)

#Prerequisites:*

##Disk Sizing:

Before upgrade, be careful to have enought space disk on the sd4 partition (you can find a tutorial here : ), it must be at least 10GB free

##DBOwner

You must then verify that the account is use to connect to the external database has the dbowner rights, you can verify that by connecting to the server where the database is store

```markdown
[root@ESX:~] passwd
```
It will prompt you yo choose a new password.

**Account loocked:**

Probably your account is lookced by too many tries, you will need to reset the number of attempts.
You can use the command `pam_tally2` with the flag `-reset`

```markdown
[root@ESX:~] pam_tally2 -user root -reset
```

**Conclusion:**

For one time you can say thank you to your Nutanix Cluster.
