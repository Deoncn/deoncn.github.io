---
layout: mypost
title: BBR 加速Debian
categories: [WEB]
---


<font face="仿宋" color=red>BBR（Bottleneck Bandwidth and RTT）</font>是一个网络拥塞算法，可以快速确定网络瓶颈并进行相应调整，以实现网络加速，同时还能稳定你的网络连接。BBR并不需要额外的硬件设备或网络基础设施，它只需要在你的电脑上进行简单的配置就可以使用。

使用BBR 阻塞算法虽然加快了服务器的吞吐量，但造成的影响是丢包。

个人不建议正常的生产服务器 不建议开启 BBR 。

```
# 查看系统内核
uname -r

# 下载 一键安装脚本（非破坏内核版）
wget -O tcpx.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcpx.sh" && chmod +x tcpx.sh && ./tcpx.sh

```

相关链接：

[Linux-NetSpeed](https://github.com/ylx2016/Linux-NetSpeed)

[有关 BBR 吞吐量及丢包率的最新文章](https://dropbox.tech/infrastructure/evaluating-bbrv2-on-the-dropbox-edge-network#appendix-d-nginx-throughput-graphs)
