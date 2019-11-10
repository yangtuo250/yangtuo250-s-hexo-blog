---
title: Hexo yilia theme 更换 & 新增功能
date: 2019-11-09 20:12:02
category: blog
tags: [blog, front-end, hexo, yilia]
wordcount: true
---

## 一 更换 yilia主题

### 1 下载

在blog root下

```bash
git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
```
<!-- more -->

### 2 安装插件

```bash
npm i hexo-generator-json-content --save
```

### 3 配置

在blog root下的```_config.yml```中新增

```yml
jsonContent:
  meta: false
  pages: false
  posts:
    title: true
    date: true
    path: true
    text: false
    raw: false
    content: false
    slug: false
    updated: false
    comments: false
    link: false
    permalink: false
    excerpt: false
    categories: false
    tags: true
```

## 二 增加文章字数统计 & 时间统计

### 1 安装插件

在blog root下

```bash
npm i --save hexo-wordcount
```

### 2 修改配置

在blog root下的```_config.yml```中新增

```yml
word_count: true
```

### 3 字数 & 时间统计

在blog root下的```theme/yilia/layout/_partial/post```新增```word.ejs```

```javascript
<div style="margin-top:10px;">
    <span class="post-time">
        <span class="post-meta-item-icon">
            <i class="fa fa-keyboard-o"></i>
            <span class="post-meta-item-text"> 废话字数: </span>
            <span class="post-count"><%= wordcount(post.content) %>字</span>
        </span>
    </span>

    <span class="post-time">
        &nbsp; | &nbsp;
        <span class="post-meta-item-icon">
            <i class="fa fa-hourglass-half"></i>
            <span class="post-meta-item-text"> 浪费时长: </span>
            <span class="post-count"><%= min2read(post.content) %>分</span>
        </span>
    </span>
</div>
```

在```theme/yilia/layout/_partial/artical.ejs```中```/artical/div[@class="article-inner"]/header[@class="article-header"]```的```if (!post.noDate) {}```中增加

```javascript
<% if(theme.word_count && !post.no_word_count){%>
    <%- partial('post/word') %>
<% } %>
```

## 三 增加访问统计

### 1 网站访问统计

在```theme/yilia/layout/_partial/footer.ejs```中增加

```javascript
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```

并在```/footer/div/div/div[@class="footer-left"]```(在左边)或者新增```/footer/div/div/div[@class="footer-middle"]```（在中间）增加

```javascript
<span id="busuanzi_container_site_uv">
    有<span id="busuanzi_value_site_uv"></span>人迷路了
</span>
```

### 2 文章访问统计

在```theme/yilia/layout/_partial/artical.ejs```中```/artical/div[@class="article-inner"]/header[@class="article-header"]```中增加

```javascript
<% if ( !index ){ %>
    <span class="archive-article-date">
    没品位的人 <span id="busuanzi_value_page_pv"></span>
    </span>
<% } %>
```
