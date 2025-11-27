# Navigation
部署个人导航主页

![屏幕截图 2025-11-27 204217](https://github.com/user-attachments/assets/94913d28-16a3-48a8-8753-62cf6aee3eaa)

核心功能亮点：
极简部署：只需一个 .html 文件，扔进 NAS 的 Web 文件夹即可。

数据持久化：使用浏览器 LocalStorage，无需数据库，无需登录，刷新不丢失。

动态侧边栏：包含实时时钟、农历（支持中文）、实时天气（基于 Open-Meteo，免费无需 Key）。

完全可编辑：界面上直接添加分类、添加链接、删除修改。

自动获取图标：输入网址自动尝试抓取 Favicon。
如何部署到 NAS
方案 A：Web Station (群晖 Synology)
确保已安装 Web Station 和 Nginx/Apache。

将上面的代码保存为 index.html。

上传文件到群晖的 /web 文件夹中（或者你自己创建的虚拟主机根目录）。

直接在浏览器输入 http://你的NAS_IP/ 即可访问。

方案 B：Docker (通用)
如果你想用 Docker 部署，可以使用极简的 Nginx 镜像：

创建一个文件夹（例如 /docker/mynav），把 index.html 放进去。

运行命令：

Bash

docker run -d -p 8080:80 \
  -v /volume1/docker/mynav:/usr/share/nginx/html \
  --name mynav nginx:alpine
访问 http://你的NAS_IP:8080。

功能使用指南
天气设置：初次加载左侧天气会提示“选择城市”。点击它，输入城市名的拼音（如 Beijing 或 Shanghai），回车搜索，点击列表中的结果即可保存。

添加内容：点击右上角的蓝色 + 添加 按钮。

链接：输入标题和网址，选择分类。

新分类：切换 Tab 到“新分类”，输入名称（如“影音娱乐”）。

编辑/删除：

鼠标悬停在链接上，右上角会出现编辑（笔）和删除（叉）图标。

鼠标悬停在分类标题上，会出现删除分类的图标。

数据备份：点击搜索栏右侧的 下载图标，可以将当前的配置导出为 JSON 文件（以防清除浏览器缓存导致数据丢失）。

图标选择方式：

自动获取 (Auto)：尝试使用 Google API（默认）。

内置图标 (Icon)：使用 FontAwesome 图标库（内置了几个常用图标供快速选择，也可以手动输入图标代码，如 fa-solid fa-server）。这非常适合内网 NAS 服务（如 Docker, Portainer, Plex 等）。

自定义图片 (URL)：你可以粘贴一个内网图片的地址（例如 http://192.168.1.5/icons/plex.png）。
