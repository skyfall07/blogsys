---
title: "Reset ESX Password with Nutanix"
categories:
  - Post Formats
tags:
  - image
  - Post Formats
---

Di you find yourself in the situation where the root account of your ESX is loocked or/and you forgot the password ? And there is no other way than reset the ESXi to retreive access ? In the case your cluster of ESX is deployed with Nutanix, here a easy way to reset your password without destroying your ESX.


**Connect to ESX with Nutanix CVM:**

First connect to one of the CVM of your cluster, and then ssh to the ESX

```html
nutanix@CMV : ~$ ssh root@ESX_IP_ADRESS
```

Then directly press Enter, no need to enter root password (hopefully for us in that case)

**Chnage root password:**

You normally already log with the root account, so just enter the passwd command :

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

