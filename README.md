# XUGOU - 基于CloudFlare搭建的轻量化监控平台

<div align="center">

![XUGOU Logo](frontend/public/logo.svg)

XUGOU 是一个基于 CloudFlare 的轻量化系统监控平台，提供系统监控和状态页面功能。

[English](./README_EN.md) | 简体中文

</div>

## 📅 开发计划

目前已实现的主要功能：

- ✅ 系统监控 - 客户端资源监控与数据上报
- ✅ HTTP 监控 - API 接口健康检测
- ✅ 数据可视化 - 实时数据展示与历史趋势
- ✅ 状态页面 - 可定制的服务状态页面
- ✅ 告警通知 - 异常事件通过多渠道通知（电子邮件、Telegram等）
- ❌ 移动APP - 方便在手机查看监控状态（维护不过来，后面打算将pwa实现好，就这样吧）

## ✨ 核心特性

- 🖥️ **系统监控**
  - 实时监控 CPU、内存、磁盘、网络等系统指标
  - 支持自定义监控间隔
  - 全平台支持（agent由go编写，理论上go能编译的平台都可以支持）

- 🌐 **HTTP 监控**
  - 支持 HTTP/HTTPS 接口监控
  - 自定义请求方法、头部和请求体
  - 响应时间、状态码和内容检查

- 📊 **数据可视化**
  - 实时数据图表展示
  - 自定义仪表盘

- 🌍 **状态页面**
  - 自定义状态页面
  - 支持多监控项展示
  - 响应式设计

## 🏗️ 系统架构

XUGOU 采用现代化的系统架构，包含以下组件：

- **Agent**: 轻量级系统监控客户端
- **Backend**: 基于 Hono 开发的后端服务，支持部署在 Cloudflare Workers 上
- **Frontend**: 基于 React + TypeScript 的现代化前端界面

## 🚀 快速开始

### 部署指南

默认用户名：admin 默认密码: admin123

准备数据库
Dashboard 操作

    登录到 Cloudflare

访问左侧菜单栏 存储和数据库 -> D1 SQL 数据库，创建一个数据库，并且记住数据库 ID 和 数据库 name

d1
部署后端服务
Dashboard 操作

手动 fork，不要使用 cloudflare 的 "通过 Git URL 克隆存储库"

1、fork 仓库 https://github.com/zaunist/xugou

2、修改仓库根目录的 wrangler.toml 文件中的数据库ID，改成前面保存的ID
3、 访问 cloudflare 的 Workers 和 Pages，创建一个 worker，并在导入存储库位置选择刚才 fork 的 xugou 仓库。

workers 构建命令：pnpm run build

4、保持根目录设置（不需要修改路径），直接点击 保存并部署

    注意：现在前后端已经集成在一个 Worker 中，不需要单独部署 Pages。Worker 会自动处理前端静态文件的服务。





## 📄 开源协议

本项目采用 MIT 协议开源，详见 [LICENSE](./LICENSE) 文件。

## 🔥 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=zaunist/xugou&type=Date)](https://www.star-history.com/#zaunist/xugou&Date)
