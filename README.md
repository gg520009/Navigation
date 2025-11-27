# Navigation
部署个人导航主页

![屏幕截图 2025-11-27 204217](https://github.com/user-attachments/assets/94913d28-16a3-48a8-8753-62cf6aee3eaa)

# 🚀 Infinity Dashboard - 极简毛玻璃个人导航页

[![Tech Stack](https://img.shields.io/badge/Vue.js-3-4FC08D?style=for-the-badge&logo=vue.js)](https://vuejs.org/)
[![Styling](https://img.shields.io/badge/Tailwind_CSS-3.x-06B6D4?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Deployment](https://img.shields.io/badge/Deployment-Static%20HTML-blue?style=for-the-badge&logo=html5)]()

## 📝 项目简介 (Introduction)

**Infinity Dashboard** 是一个高性能、外观精美的个人起始页 (Startpage)，旨在提供一个快速、可自定义的网页导航中心。

项目采用现代的 **毛玻璃 (Glassmorphism)** UI 设计，并专注于 **零后端依赖**。这意味着您无需配置数据库或用户登录系统，所有数据都安全地存储在您的浏览器本地，特别适合部署在个人 NAS 或内网环境中。

## ✨ 核心特性 (Features)

* **⚡ 零依赖部署：** 纯 HTML/CSS/JS 文件，只需一个静态文件服务器即可运行（例如 Nginx 或 NAS Web Service）。
* **🔒 无需登录：** 配置数据 (Links/Categories/Settings) 基于浏览器 LocalStorage 持久化存储，刷新不丢失。
* **🎨 视觉美学：** 采用 Vue 3 + Tailwind CSS 构建，实现流畅且令人印象深刻的毛玻璃效果。
* **📅 智能侧边栏：** 实时显示当前时间、星期、基于城市的实时天气，以及完整的 **中国农历** 信息。
* **🔧 轻松定制：** 所有链接、分类均可在页面中直接通过 UI 界面添加、编辑和删除。
* **🔗 图标优化：** 内网环境支持手动选择 **FontAwesome 图标代码** 或 **自定义图片 URL**。

## 📸 效果预览 (Preview)

<p align="center">
  <img src="./screenshots/preview.png" alt="Infinity Dashboard Screenshot" width="850" style="border-radius: 10px; box-shadow: 0 10px 30px rgba(0,0,0,0.5);">
</p>

## 🚀 快速部署 (Quick Start)

项目本质上是一个单页应用 (SPA)，部署过程极其简单，您只需要一个 `index.html` 文件。

### 方式一：NAS 静态网页托管 (推荐)

1.  将项目代码保存为 `index.html` 文件。
2.  将 `index.html` 上传至您的 NAS (如 Synology/QNAP) 的 Web 服务根目录（通常是 `/web` 文件夹）。
3.  通过浏览器访问 `http://您的NAS_IP/` 即可。

### 方式二：Docker 容器部署

如果您希望通过 Docker 部署，可以使用轻量级的 Nginx 镜像进行托管：

```bash
docker run -d \
  --name infinity-dashboard \
  -p 8080:80 \
  -v /path/to/your/index.html/folder:/usr/share/nginx/html \
  nginx:alpine
