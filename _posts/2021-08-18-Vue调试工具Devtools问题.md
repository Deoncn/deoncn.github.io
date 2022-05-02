---
date: 2021-08-18 08:50:13
layout: mypost
title: Vue调试工具Devtools不出现的解决方式
categories: 
---
Vue调试工具从高往下兼容，使用最高版本没有不兼容旧的问题。开发者工具若一直是灭的，首先检查Vue是否使用了压缩版本，压缩版本的Vue 无法使用开发者工具，所以一直是灰色图标。

```text
https://github.com/vuejs/vue-devtools
 
1. If the page uses a production/minified build of Vue.js, devtools inspection is disabled by default so the Vue pane won't show up.
2. To make it work for pages opened via file:// protocol, you need to check "Allow access to file URLs" for this extension in Chrome's extension management panel.

```