---
layout: mypost
title: 友情链接
---
```
<script>
  fetch('https://v1.hitokoto.cn')
    .then(response => response.json())
    .then(data => {
      const hitokoto = document.getElementById('hitokoto_text')
      hitokoto.href = 'https://hitokoto.cn/?uuid=' + data.uuid
      hitokoto.innerText = data.hitokoto
    })
    .catch(console.error)
</script>				<!--一言Javascript + html-->

<p id="hitokoto_text">:D 获取中...</p> 
```

<h1>学业</h1>
<a href="https://onlineh5.zhihuishu.com/onlineWeb.html#/studentIndex" target="_blank">智慧树 - 在线学堂</a><br/>
<a href="http://i.chaoxing.com/base?t=1616781552987" target="_blank">学习通 - 个人空间</a><br/>
<a href="https://www.icourse163.org/" target="_blank">中国大学MOOC(慕课)</a><br/>
<a href="https://www.yuketang.cn/web" target="_blank">雨课堂网页版</a><br/>
<a href="http://www.neea.edu.cn/" target="_blank">中国教育考试网</a><br/>
<a href="http://jwgl.xawl.edu.cn/" target="_blank">西安文理学院教务管理系统（old）</a><br/>
<a href="http://jwglnew.xawl.edu.cn/" target="_blank">西安文理学院教务管理系统(新)♥</a><br/>

<h1>Javadopsway</h1>
<a href="https://www.w3school.com.cn/h.asp" target="_blank">V3School - HTML 系列教程</a><br/>
<a href="https://www.51zxw.net" target="_blank">我要自学网</a><br/>
<a href="https://v3.bootcss.com/css/#tables-hover-rows" target="_blank">Bootstrap v3 中文文档</a><br/>
<a href="https://www.runoob.com" target="_blank">菜鸟教程 - 学的不仅是技术，更是梦想！</a><br/>
<a href="https://education.github.com/pack/offers?sort=popularity&tag=Learn" target="_blank">GitHub Student Developer Pack</a><br/>
<a href="https://github.com/deoncn" target="_blank">我的Github</a><br/>

<h1>Brand Trojan</h1>
<a href="https://brand.dynv6.net/config/" target="_blank">Brand Trojan Panel</a><br/>
<a href="https://console.dogecloud.com/" target="_blank">DogeCloud 云加速及视频</a><br/>
<a href="https://dynv6.com/" target="_blank">dynv6.net Free域名</a><br/>
<a href="https://cvm.dogyun.com/server/list" target="_blank">狗云</a><br/>


<p id="hitokoto_text">:D 获取中...</p>

<hr/>
© Deoncn 2021