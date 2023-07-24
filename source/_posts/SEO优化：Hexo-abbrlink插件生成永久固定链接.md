---
title: SEO优化：Hexo-abbrlink插件生成永久固定链接
id: Hexo-abbrlink
tags:
  - Hexo
  - abbrlink
  - 前端
categories: 前端开发
cover: 'https://img01.anheyu.com/useruploads/224/2023/07/22/64bbe8681bec5.png'
abbrlink: a1e8a28a
date: 2023-07-22 22:25:36
---
## SEO优化：Hexo-abbrlink插件生成永久固定链接

### 初衷
之前一直困扰了很长一段时间，写完博客，访问博客文章链接很长，中文直接转`UTF-8编码`了，导致对分享链接来说很不友好。经过询问博友们，这让我接触到了`Hexo-abbrlink`。
![](https://img01.anheyu.com/useruploads/224/2023/07/22/64bbe8681bec5.png)

### 关于Hexo-abbrlink
`Hexo-abbrlink`是一个 [Hexo 插件](https://hexo.io/plugins/)，用于基于文章标题和前置数据生成静态文章链接，是博客链接永久化的解决方案。
该插件支持 `.textbundle` 格式 -- 一种包含 markdown 和相关资源的文件格式。实际上，`.textbundle` 文件是一个文件夹，在 macOS 的 Finder 中显示为文件。

### 安装方法

将插件添加到 Hexo：

```
npm install hexo-abbrlink --save
```

修改 `config.yml` 文件中的永久链接：

```
permalink: posts/:abbrlink/ 
# 或
permalink: posts/:abbrlink.html
```

有两个设置：

```
alg -- 算法（目前支持 crc16 和 crc32，其中 crc16 是默认值）
rep -- 表示（生成的链接可以用十六进制或十进制表示）
```

```
# abbrlink config
abbrlink:
  alg: crc32      # 支持 crc16（默认）和 crc32
  rep: hex        # 支持 dec（默认）和 hex
  drafts: false   #（true）处理草稿，（false）不处理草稿。false（默认）
  # 从目录树生成类别
  # depth：您要生成的目录树的最大深度，应> 0
  auto_category:
     enable: true  # true（默认）
     depth:        # 3（默认）
     over_write: false 
  auto_title: false # 启用自动标题，可以通过路径自动填充标题
  auto_date: false # 启用自动日期，可以通过今天的时间自动填充日期
  force: false # 启用强制模式，在此模式下，插件将忽略缓存，并为每篇文章计算 abbrlink，即使它已经有 abbrlink。这只更新 abbrlink 而不是其他前置变量。
```

#### 示例

生成的链接将如下所示：

```
crc16 & hex
https://blog.zhaoziyi.site/posts/a1e8a28a.html

crc16 & dec
https://blog.zhaoziyi.site/posts/dc5e24b.html
```
### 限制

[fixed] 最大文章数为 65535（对于crc16）.（现在，如果已存在 abbrlink，则会更改另一个并一遍又一遍地尝试...）

### 报错解决方案
经过百般努力，这个配置完成之后，文章的链接都变成了undefined （如图所示），新的文章没问题，老的文章就不行了。这个问题其实仔细想一下就能明白，我们首先要执行`hexo clean` 清楚掉以前生成的文章缓存，然后`hexo generate`重新渲染就ok了。
![](https://img01.anheyu.com/useruploads/224/2023/07/22/64bbe824b2896.png)

### 关于插件的更多信息
参考：[https://github.com/rozbo/hexo-abbrlink2](https://github.com/rozbo/hexo-abbrlink2)

### 成果
总体来看，效果还是蛮不错的，耶比耶比~