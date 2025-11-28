---
title: GFW vs 各种翻墙技术
published: 2025-11-23
description: 仅仅只是技术科普无任何政治倾向
tags:
  - GFW
  - Clash
  - V2ray
draft: true
pinned: false
lang: ""
---
# 免责声明（先叠个甲）
本文章只是一个普通的技术科普类视频，没有任何政治倾向

# 轻量化加密

## Shasowsocks(一代传奇)

2012年4月22日，一位网名为`clowwindy`的中国程序员在GitHub上发布了一个名为`Shadowsocks`的项目  
Shadowsocks是一种加密代理协议也是一个加密代理工具。它通过加密你的流量从而突破网络限制，访问被屏蔽的网站  
这个项目已发布就火爆全网，在那时，那个印有小飞机图标的客户端几乎成为了当时翻墙用户的标配  
然而好景不长，2015年8月22日，clowwindy在GitHub上留下了这一段话  
>Two days ago the police came to me and wanted me to stop working on this. Today they asked me to delete all the code from GitHub. I have no choice but to obey.
>两天前警察找到了我，希望我停止开发这个项目。今天他们让我删掉GitHub上的所有代码，我别无选择，只能服从。

这就是著名的`喝茶事件`  
这本应是Shadowsocks的终点，但谁也没想到，这反而成了它"永生"起点  
因为Shadowsocks的代码是开源的，它的代码早已传遍整个GitHub社区。当clowwindy删库之后，马上就有社区的开发者站出来接管了此项目，使Shadowsocks的火种延续了下去，这就是开源的力量  
现在Shadowsocks的流量特征已经能被GFW准确识别并封杀了，只要你一搭建Shadowsocks的代理服务器，不一会就会被封掉。目前只有专线机场还在用Shadowsocks，因为专线机场的流量不经过GFW，所以不存在被识别和封杀的问题。对于普通用户来说Shadowsocks已经基本退出了历史的舞台  

## ShadowsocksR(备受争议)
ShadowsocksR是Shadowsocks的一个著名分支，它加入了协议混淆和加密方式，号称更安全更难被识别，在当时火爆程度不输Shadowsocks  
但是ShadowsocksR的作者与Shadowsocks社区关系紧张，引发了大量的争议。最终ShadowsocksR的作者在经历大量的人肉搜索和网络攻击后，一怒之下删除了此项目  
如今ShadowsocksR基本退出了历史舞台，成为了时代的眼泪

# VMess(为墙而生)
随着GFW的升级，它开始具备了流量分析和主动探测的能力，能够识别出Shadowsocks的流量特征。为了应对这种情况，新的加密协议应运而生，它的核心思想就是"伪装"  
当Shadowsocks被GFW大规模封锁后，一个名为`V2ray`的项目带着它的核心协议`VMess`异军突起  
VMess就是为了对抗GFW的流量识别而设计的