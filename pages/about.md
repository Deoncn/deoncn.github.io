---
layout: page
title: 关于
---
<video width="100%" controls=""><source src="https://s-bj-2339-mydisk1.oss.dogecdn.com/%E3%81%82%E3%81%AE%E3%81%AF%E3%81%AA.mp4" type="video/mp4"></video>


<p>Hello 陌生人，欢迎访问我的博客，目前的主要任务是大学毕业。
联系我 QQ 2210633536 <a href="http://mail.qq.com/cgi-bin/qm_share?t=qm_mailme&email=YBQNAQkaBSAREU4DDw0" target="_balnk">📫邮箱</a> 
<a href="https://github.com/deoncn" target="_balnk">Github</a>

</p>

👨‍👦‍👦 欢迎各位朋友与我建立友链，如需友链请到<a href="{{ site.tucaoUrl}}" target="_blank">留言板</a>留言，我看到留言后会添加上的，本站的友链信息如下

```html
名称：{{ site.title }}
描述：{{ site.description }}
地址：{{ site.domainUrl }}{{ site.baseurl }}
头像：{{ site.headerimg }}
```

<ul>
  {%- for link in site.links %}
  <li>
    <p><a href="{{ link.url }}" title="{{ link.desc }}" target="_blank" >{{ link.title }}</a></p>
  </li>
  {%- endfor %}
</ul>
