# Navigation
部署个人导航主页

![屏幕截图 2025-11-27 204217](https://github.com/user-attachments/assets/94913d28-16a3-48a8-8753-62cf6aee3eaa)

🚀 Infinity Dashboard - 极简毛玻璃个人导航页简介Infinity Dashboard 是一个专为个人和内网环境设计的极简、高性能的浏览器起始页。它无需复杂的后端、无需数据库、无需用户登录，所有配置数据（链接、城市设置）都安全地存储在您的浏览器本地，真正实现了“即插即用”和“轻松部署”。✨ 核心特性功能模块描述优势🎨 惊艳 UI采用流行的 毛玻璃 (Glassmorphism) 设计风格，视觉效果美观、现代。提升个人 NAS 体验，视觉效果出众。🔒 无需登录所有数据基于浏览器 LocalStorage 持久化存储。部署零配置，数据编辑后即时保存。☁️ 智能侧边栏集成实时时钟、天气预报 (Open-Meteo) 和完整的 中国农历 显示。小巧且功能强大的信息中心。🔗 高度自定义支持在页面中直接添加、编辑、删除分类和链接。维护简单直观。🖼️ 图标兼容支持 自动获取 Favicon；内网用户可手动选择 FontAwesome 图标或输入自定义 URL。彻底解决内网环境图标显示问题。📸 效果预览<p align="center"><img src="./screenshots/preview.png" alt="Dashboard Preview Screenshot" width="800" style="border-radius: 10px; box-shadow: 0 10px 30px rgba(0,0,0,0.5);"></p>🚀 部署指南由于项目仅包含一个 HTML 文件，部署极为简单。方式一：NAS 静态网页托管 (Synology/QNAP)将项目代码保存为 index.html。将 index.html 文件上传至您的 NAS 的 Web 服务目录（例如群晖的 /web 文件夹）。通过浏览器访问 http://您的NAS_IP/index.html 即可使用。方式二：Docker 容器部署 (推荐)如果您习惯使用 Docker，可以使用轻量级 Nginx 镜像进行托管：创建本地文件夹（如 ~/data/infinity-dash），将 index.html 放入其中。运行 Docker 命令：Bashdocker run -d \
  --name infinity-dashboard \
  -p 8080:80 \
  -v ~/data/infinity-dash:/usr/share/nginx/html \
  nginx:alpine
访问 http://您的NAS_IP:8080。⚙️ 使用说明添加内容： 点击右上角的 + 添加 按钮，您可以选择添加新的链接或新的分类。编辑链接： 鼠标悬停在任一链接卡片上，右上角会出现铅笔图标，点击即可编辑链接信息和图标类型。设置天气： 点击左侧天气卡片中的 切换 按钮，输入城市名称（支持拼音），选择后即可保存。⚠️ 注意： 由于数据保存在浏览器本地，请勿清空浏览器缓存，或定期点击右上角的 下载图标 进行配置备份。
