---
title: 随机图站点搭建
published: 2026-06-28
description: 手把手带你用CF搭建一个随机图站点
image: ../assets/images/randompic.png
tags:
  - CloudFlare
  - Github
draft: false
pinned: false
lang: ""
---
**通过[afoim（二叉树树）](https://2x.nz)开源的随机图站点代码 [Static_RandomPicAPI-Github](https://github.com/afoim/Static_RandomPicAPI) 以及CloudFlare提供的免费站点部署来搭建一个属于你的随机图站点**

# 所需物品

1. 一个CloudFlare账号
2. 一个Github账号
3. 一双手
4. 一个脑子


---

# 操作步骤

## 克隆仓库

~~来到仓库主页[Static_RandomPicAPI-Github](https://github.com/afoim/Static_RandomPicAPI)，点击右上角的fork~~

现在的这个仓库二叉树树将build.js中生成html前端页面的部分删除了，推荐fork以前的这个版本  
::github{repo="AT13xe/Static_RandomPicAPI"}

**项目结构**  

```
ri/
├─ h/          # 横屏图片
├─ v/          # 竖屏图片
├─ build.js    # 构建脚本
└─ config.json # 配置文件
```

将你所要展示的图片放在`ri/`这个目录即可  

将`config.json`中的域名改成自己的即可
```Json [config.json]
{
    "domain": "https://你这个项目绑定的域名"
}
```

## 部署站点

打开`Cloudflare`中的`Workers and Pages`  

### Workers部署

点击右上角的创建应用程序，选择Continue with Github，选择你fork的仓库。在`构建命令`那一栏中填写`node build.js`，最后点击部署，给项目绑定一个自定义就大功告成了。

### Pages部署

点击右上角的创建应用程序，在弹出的方框下面有一个`想要部署Pages?开始使用`。点击开始使用，选择导入现有的Git存储库，选择你fork的仓库，点击开始设置。  
在`构建命令`那一行填写`node build.js`  
在`构建输出目录`那一行填写`dist`  
点击开始并部署，然后绑定自定义，就大功告成了


