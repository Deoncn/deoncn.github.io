---
layout: mypost
title: 友情链接
---

欢迎各位朋友与我建立友链，如需友链请到[留言板](chat.html)留言，我看到留言后会添加上的，本站的友链信息如下

```
名称：{{ site.title }}
描述：{{ site.description }}
地址：{{ site.domainUrl }}{{ site.baseurl }}
头像：{{ site.domainUrl }}{{ site.baseurl }}/static/img/logo.jpg
```

<ul>
  {%- for link in site.links %}
  <li>
    <p><a href="{{ link.url }}" title="{{ link.desc }}" target="_blank" >{{ link.title }}</a></p>
  </li>
    <li>
    <p><a href="{https://rain.moimo.me}" title="{moi的一般通过小站}" target="_blank" >{M E S}</a></p>
  </li>
  {%- endfor %}
</ul>
