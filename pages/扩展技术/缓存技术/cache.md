---
layout: post
title:  "缓存知识讲解"
date:   2017-09-28
comments: true
---

### 一：缓存的分类
- 分布式缓存：需要序列化，速度相较于本地缓存较慢，但是理论上缓存的数量与大小无限（因为缓存机器可以不断扩展）
- - A：Redis
- - B：Memcache
- 本地缓存：不需要序列化，速度快，缓存的数量与大小限制于本机内存
- - A：Google guava cache
- - B：Ehcache
- - C：Oscache
