---
title: next主题配置，继续
published: 2021-12-22 21:15:13
tags: [hexo]
category: hexo
draft: false
---

## 前言

next主题现在基本已经配置上去了，也能看了，但是我们还可以再添加点新东西

本次要完成的内容如下：

1. 配置打赏功能
2. 开启订阅公众号
3. 首页文章设置阅读全文
4. 添加动态背景
5. 给博客添加fork Github
6. 修改文章内链接样式
7. 修改文章底部带#的标签

## next继续配置

### 配置打赏功能

找到`next`主题下的配置文件`_config.yml`

![image.png](../imgs/hexo/07/hexo01.png)

全局搜索`rew`

![image.png](../imgs/hexo/07/hexo02.png)

![image.png](../imgs/hexo/07/hexo03.png)

![image.png](../imgs/hexo/07/hexo04.png)

![image.png](../imgs/hexo/07/hexo05.png)

最后`ctrl+S` 保存下配置文件，浏览器刷新页面，随便进入一篇文章，拉到最下面，即可看到效果

![payMoney.gif](../imgs/hexo/07/hexo06.gif)

### 开启订阅公众号

找到`next`主题下的配置文件`_config.yml`

就在配置`打赏`功能的上方，就是配置`公众号`的地方

![image.png](../imgs/hexo/07/hexo07.png)

![image.png](../imgs/hexo/07/hexo08.png)

最后`ctrl+S` 保存下配置文件，浏览器刷新页面，随便进入一篇文章，拉到最下面，即可看到效果

![image.png](../imgs/hexo/07/hexo09.png)

### 首页文章设置阅读全文

![image.png](../imgs/hexo/07/hexo10.png)

#### 有两种方式设置阅读全文(1) 直接修改配置文件

找到`next`主题下的配置文件`_config.yml`

![image.png](../imgs/hexo/07/hexo11.png)
![image.png](../imgs/hexo/07/hexo12.png)

我开启阅读全文

![image.png](../imgs/hexo/07/hexo13.png)

最后`ctrl+S` 保存下配置文件，浏览器刷新页面，进入首页，可以了

![image.png](../imgs/hexo/07/hexo14.png)

#### 有两种方式设置阅读全文(2) 在每个单个文件上加上`<!-- more -->`

`next`主题下的配置文件`_config.yml` 我先还原

![image.png](../imgs/hexo/07/hexo15.png)

然后我们打开一篇具体的文章

![image.png](../imgs/hexo/07/hexo16.png)

最后`ctrl+S` 保存下配置文件，浏览器刷新页面，进入首页，可以了

![image.png](../imgs/hexo/07/hexo17.png)

ps. 两种方式都可以实现阅读全文的效果，只是实现过程不一样：

1. 第一种只需要配置一次，所有文章都生效，都出现阅读全文的按钮
2. 第二种单独配置，只给需要折叠的文章折叠，出现阅读全文的按钮

大家各取所需

### 添加动态背景

`next`主题下的配置文件`_config.yml`

![image.png](../imgs/hexo/07/hexo18.png)

来看第一种特效

![image.png](../imgs/hexo/07/hexo19.png)

![texiao1.gif](../imgs/hexo/07/hexo20.gif)
不是特别清楚，大家可以自己实操一下

来看第二种特效

![image.png](../imgs/hexo/07/hexo21.png)

![texiao2.gif](../imgs/hexo/07/hexo22.gif)

来看第三种特效

![image.png](../imgs/hexo/07/hexo23.png)

![texiao3.gif](../imgs/hexo/07/hexo24.gif)

来看第四种特效

![image.png](../imgs/hexo/07/hexo25.png)

![texiao4.gif](../imgs/hexo/07/hexo26.gif)

第四种特效也不是特别清楚，大家可以自己实操一下

### 给博客添加fork Github

`fork Github` 就是一个在页面 左上角，或则右上角的github图标，点击就会跳转到github页面
样子长这样

![image.png](../imgs/hexo/07/hexo27.png)

地址在这里：[传送门](https://tholman.com/github-corners/)

![image.png](../imgs/hexo/07/hexo28.png)

网页往下拉，可以看到在右上角的图标

![image.png](../imgs/hexo/07/hexo29.png)

开始添加github图标操作

![image.png](../imgs/hexo/07/hexo30.png)

如果你要换别的github图标，就复制相应的代码

![image.png](../imgs/hexo/07/hexo31.png)

![image.png](../imgs/hexo/07/hexo32.png)

最后`ctrl+S` 保存下配置文件，浏览器刷新页面，可以了

直接刷新浏览器没出来效果，那么我们重新生成一下hexo

```js
再执行这3段命令

hexo clean
hexo generate
hexo server
```

![image.png](../imgs/hexo/07/hexo33.png)

点击这个github图标，也能跳转到github，不过今天github不太好访问，点过去好久，也没刷新出来，就不展示了==

### 修改文章内链接样式

默认的**Next主题**的超链接的样式是 **单纯的黑色** + **下划线**

显得有点单调且**不显眼**，挺丑的

![link.gif](../imgs/hexo/07/hexo34.gif)

我们改下

- 打开博客目录下`./themes/source/css/_custom/custom.styl`
- 在`cutom.styl` 最开始处加入如下的代码

```js
if hexo-config("custom_css.post_body_a.enable")
  .post-body
    a:not(.btn){
      color: convert(hexo-config("custom_css.post_body_a.normal_color"));
      border-bottom: none;
      &:hover {
        color: convert(hexo-config("custom_css.post_body_a.hover_color"));
        text-decoration: underline;
      }
    }
```

**PS:**  其中的 `a:not(.btn)` 是为了不影响**阅读全文按钮**

- 然后在**主题配置文件**`./themes/_config.yml`中加入`custom_css`的配置

```js
custom_css:
  # the style of post body link
  post_body_a:
    enable: true
    normal_color: "#0593d3"
    hover_color: "#0477ab"
```

![image.png](../imgs/hexo/07/hexo35.png)

后续修改**超链接**样式时，只需修改**配置文件**里面的**颜色值**即可

看看现在的效果

![link2.gif](../imgs/hexo/07/hexo36.gif)

### 修改文章底部带#的标签

![image.png](../imgs/hexo/07/hexo37.png)

打开博客目录下`./themes/layout/_macro/post.swig`

![image.png](../imgs/hexo/07/hexo38.png)

因为hexo 是默认引入奥森字体的，那么我们就去找个合适的奥森字体放进来

奥森字体，[传送门](https://www.thinkcmf.com/font/font_awesome/icons.html)

![image.png](../imgs/hexo/07/hexo39.png)

![image.png](../imgs/hexo/07/hexo40.png)

```css
<i class="fa fa-tag" aria-hidden="true"></i>
```

![image.png](../imgs/hexo/07/hexo41.png)

```js
再执行这3段命令

hexo clean
hexo generate
hexo server
```

刷新浏览器，看效果

![image.png](../imgs/hexo/07/hexo42.png)

参考文章：

1. [修改 Hexo Next 默认超链接样式](https://vonsdite.github.io/posts/13afd8d4.html)
