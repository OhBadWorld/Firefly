---
title: hexo 修改默认端口号（2种方案）
published: 2022-11-15 21:15:13
tags: [hexo]
category: hexo
draft: false
---

#### 前言

我又新建了一个hexo博客，运行时报错，提示4000端口已被占用，下面提供两钟解决方案：

- 方法一 暂时修改端口号：

修改package.json文件里的server，修改前：

```bash
"server": "hexo server"
```

修改后：

```bash
"server": "hexo server -p 4001"
```

`注意：这时候你需要用【npm run server】来开启服务。`

- 方法二 永久修改端口号：

找到hexo安装目录的node_modules\hexo-server\index.js，修改即可。

`注意：方案2是直接修改了hexo的原始文件，即便你想同时运行多个博客都不行，所以建议使用方案1且方案2我没有试过，强烈建议使用方案1。`

#### 参考文章

[hexo官网](https://hexo.io/zh-cn/)
