---
title: hexo-jenkins-建站
date: 2019-04-11 16:28:40
tags: hexo, jenkins, nginx
---

# 使用 hexo 搭建博客，jenkins 配合 github（webhook）自动部署

### hexo

1. 安装 hexo-cli
2. hexo init blog
3. hexo new 'post'
4. hexo server // 本地开发
5. hexo generate // 这步在服务器完成，这样就不用在本地生成 public 文件

---

### github

1. 配置 webhook // http://server:jenkins-port/github-webhook/

---

### jenkins

1. 安装 java
2. 安装 jenkins
3. 启动 jenkins
4. http://server:jenkins-port 打开 jenkins
5. 安装插件
6. 新建 pipeline

---

### nginx 简单配置

1. 安装 nginx
2. 在 conf.d 下新建自己的 .conf 文件
3. 运行 nginx

---

### 遇到的一些问题

1. jenkins 默认会创建一个 jenkins 的用户去使用服务器，因为权限问题，我修改 jenkins 的配置文件，默认使用 root
2. jenkins 使用 jenkins-shell，丢失了环境变量 PATH，我使用了软连接，ln -s <> /usr/local/bin
3. nginx 的权限不足的问题，直接修改 user 为 root

---

### 需要努力的地方

1. 对 Linux 环境下的权限问题理解不清，导致很多问题

---

### 参考文章

- https://juejin.im/post/5a366f7cf265da432e5c16d3