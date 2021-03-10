---
layout: mypost
title: 重命名PyCharm顶部的名称
categories: [收藏夹]
---

## ** 重命名PyCharm顶部的名称 ** ##
------
今天我遇到了同样的问题。 我试过this answer，但没有找到这个<projectdir>/.idea/.name。

所以我重新命名了<projectdir>/.idea/<projectName>.iml，但我意识到这还不够。

为了充分发挥作用，我必须：

更改项目目录的名称
重命名<projectdir>/.idea/<projectName>.iml文件
重建virtualenv（因为我在这个模块上使用了它）
更改文件夹.idea中每个xml文件中文件<projectName>.iml和virtualenv目录（在我的示例中是文件名：modules.xml和workspace.xml->；这是所有项目的主目录）的所有路径
更改xml文件（在我的例子中是：workspace.xml）中的模块（projectName）的名称，每行包含：

<favorites_list name="<projectName>" />

<option name="myItemId" value="<projectName>" />

<module name="<projectName>" />

<ignored path="<projectName>.iws" />->；但我对这一点不是百分之百确定。

最后重新启动pyCharm并将当前virtualenv设置为Python解释程序
信息：我正在为pyCharm社区版2016.2和Ubuntu16.04LTS工作。

如果有人知道更简单的方法，请随时通知我。


# 👉  [原文](https://www.cnpython.com/qa/101145)