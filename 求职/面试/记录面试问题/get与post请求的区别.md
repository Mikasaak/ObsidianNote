---
description: 
pubDate:
tags: 
title: get与post请求的区别
date_created: 2024-05-16日 星期四 , 03:42:05 下午
date_modified: 2024-05-16日 星期四 , 04:01:27 下午
---
get是用来获取数据
post是提交数据

参数位置
get--在url
pos--请求体

参数长度
get--有限制（浏览器or服务器的限制）
pos--无限制

get--请求参数回存储在浏览器历史记录里 post不会
get请求返回的内容会默认存在浏览器缓存中 post需要自己配置

GET在浏览器回退时是无害的，而POST会再次提交请求。

get产生的URL地址触发bookmark

get请求只支持ASCII字符 post无限制



