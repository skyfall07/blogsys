---
title: "Reset ESX Password with Nutanix"
categories:
  - Post Formats
tags:
  - image
  - Post Formats
---

Di you find yourself in the situation where the root account of your ESX is loocked or/and you forgot the password ? And there is no other way than reset the ESXi to retreive access ?`/assets/images/` In the case your cluster of ESX is deployed with Nutanix, here a easy way to reset your password without destroying your ESX`{% raw %}{{ site.url }}{{ site.baseurl }}/assets/images/{% endraw %}` .



**Nutanix CVM:**

First connect to one of the CVM of your cluster, and then ssh to the ESX

```html
nutanix@CMV : ~$ ssh root@ESX_IP_ADRESS
```

**or Kramdown:**

```markdown
{% raw %}![alt]({{ site.url }}{{ site.baseurl }}/assets/images/filename.jpg){% endraw %}
```

![Unsplash image 9]({{ site.url }}{{ site.baseurl }}/assets/images/unsplash-image-9.jpg)

Image that fills page content container by adding the `.full` class with:

**HTML:**

```html
{% raw %}<img src="{{ site.url }}{{ site.baseurl }}/assets/images/filename.jpg" alt="" class="full">{% endraw %}
```

**or Kramdown:**

```markdown
{% raw %}![alt]({{ site.url }}{{ site.baseurl }}/assets/images/filename.jpg)
{: .full}{% endraw %}
```

![Unsplash image 10]({{ site.url }}{{ site.baseurl }}/assets/images/unsplash-image-10.jpg)
{: .full}
