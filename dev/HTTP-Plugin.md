# RW-HPS - HTTP API 开发规范

> 注:
> - 本章节展示关于 `RW-HPS-http-api` 开发规范

## 前言

为了便于玩家开发 同时减少 HTTP 通用的干扰  
我们编写了本文档

## 统一状态码

我们建议全部返回 `HTTP:200`  
减少 JavaScript Okhttp 对错误码的另外处理

## 统一数据返回格式

对外开放服务 我们统一建议使用 `Json` 作为数据返回

### 统一路径

对外提供 `API` 服务的 `Plugin` 路径为  
`ip:port/plugin/插件名称`  
对于 `GET` 建议使用  
`ip:port/plugin/api/get`  
对于 `POST` 建议使用
`ip:port/plugin/api/post`
