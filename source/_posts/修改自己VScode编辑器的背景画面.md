---
title: 修改VScode编辑器的背景画面
id: vscode-background
tags: vscode
categories: 前端开发
cover: 'https://cccimg.com/view.php/51a16a1e0c1c9e990ee72852a9997a59.jpg'
abbrlink: dc5e24b
date: 2023-07-22 20:16:35
---
## 如何修改自己VScode编辑器的背景画面
### 开始
作为一名热爱编程的<s> 程序牛 </s>，我对自己使用的软件编辑器自然有一些小小的改进想法。接下来，将介绍如何让编辑器更加美观和实用，下面就来为大家介绍一下怎么给它扮靓靓啦...
### 安装插件 
首先打开VScode软件，按快捷键 Ctrl+Shift+x，打开扩展商店，搜索 background 并安装。
![](https://cccimg.com/view.php/1305bd323e401e8557df12a0ac3767c5.png)
### 设置插件
文件 - 首选项 - 设置 ， 然后输入 background，显示扩展设置，点击 "在settings.json中编辑"。
![](https://cccimg.com/view.php/5d78d00641f0cc759cb7649f954bec1d.png)
### 填写代码
输入以下代码设置背景图片的样式，注意：要在大括号里面输入；图片选自己喜欢看的，但路径和格式不能错；透明度可以根据自己需求设置。代码在最后面，可以直接复制粘贴。
```CSS
    "background.style": {
        "content": "''",
        "pointer-events": "none",
        "position": "absolute", // 绝对定位
        "z-index": "99999",
        "width": "100%",
        "height": "100%",
        // "background-position": "0% 0%", // 图片位置
        "background-size": "cover", // 图片大小，这里设置铺满
        // "background-size": "50%,50%", //如果缩放的话就输出缩放的百分比
        "background-repeat": "no-repeat", //是否重复
        "opacity": 0.3 // 透明度
    },
    "background.customImages": [
        "file:///C:/Users/Administrator/Pictures/image.jpg" // 本地图片地址
    ],
    "background.useDefault": false, //是否使用默认图片,false
```
![](https://cccimg.com/view.php/543ad7642a806b1a956f27ce0068eb91.png)
### 重启VScode
设置完按ctrl+s 保存之后，会弹出让你重启VScode。
![](https://cccimg.com/view.php/864c29de967f7eb1ff11b64fb6020ef0.png)
如果没有成功，请**使用管理员身份**运行vscode。
![](https://cccimg.com/view.php/c72ac580cca142a0dcc5335c3397bc33.png)
重启之后随便新建一个文件，惊不惊喜，意不意外？

