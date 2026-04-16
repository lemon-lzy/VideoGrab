# VideoGrab - 视频下载神器

基于 yt-dlp + 抖音专用模块 的万能视频下载网站，支持 1800+ 平台视频下载。

![image-20260416191203709](C:\Users\xier\AppData\Roaming\Typora\typora-user-images\image-20260416191203709.png)

![image-20260416191249578](C:\Users\xier\AppData\Roaming\Typora\typora-user-images\image-20260416191249578.png)

![image-20260416191354571](C:\Users\xier\AppData\Roaming\Typora\typora-user-images\image-20260416191354571.png)

## 技术栈

- **前端**: Vue 3 + Vite + Tailwind CSS
- **后端**: FastAPI（Python）
- **核心能力**:
  - yt-dlp — 支持 YouTube、Bilibili、Twitter/X 等 1800+ 平台
  - 抖音专用模块 — 通过公开 API 解析，无需登录和 Cookie
  - H.264 编码转换 — 自动转换视频格式，兼容手机微信

## 快速开始

### 1. 启动后端

```bash
cd backend
pip install -r requirements.txt
python main.py
```

后端服务运行在 http://localhost:8000 ，API 文档: http://localhost:8000/docs

### 2. 启动前端

```bash
cd frontend
npm install
npm run dev
```

前端运行在 http://localhost:5173

## 核心功能

- **一键解析**: 粘贴视频链接，自动识别平台，智能解析视频信息
- **多种清晰度**: 从 360p 到 4K，多种格式可选
- **智能下载**: 服务端代理下载，解决防盗链问题
- **抖音支持**: 无需 Cookie，通过公开 API 直接获取无水印视频
- **H.264 转码**: 自动检测 HEVC 编码并转换为 H.264，兼容手机微信播放
- **移动端适配**: 响应式设计，手机浏览器也能使用

## 支持平台

| 平台 | 引擎 | 说明 |
|------|------|------|
| 抖音 | 专用模块 | 无需登录，无水印下载 |
| YouTube | yt-dlp | 多清晰度，含音频合并 |
| Bilibili | yt-dlp | 支持多 P 视频，自动 H.264 转码 |
| Twitter/X | yt-dlp | 推文视频下载 |
| TikTok | yt-dlp | 需海外 IP |
| 其他 1800+ | yt-dlp | Instagram、Facebook、Vimeo 等 |

## 项目结构

```
├── backend/             # FastAPI 后端
│   ├── main.py          # API 路由入口
│   ├── downloader.py    # yt-dlp 封装（通用平台）+ H.264 转码
│   ├── douyin.py        # 抖音专用解析模块
│   ├── ffmpeg/          # ffmpeg 工具目录
│   └── requirements.txt
├── frontend/            # Vue3 前端
│   └── src/
│       ├── components/  # UI 组件
│       ├── api/         # API 调用
│       └── App.vue      # 根组件
└── README.md
```

## API 接口

| 方法 | 路径 | 说明 |
|------|------|------|
| POST | /api/parse | 解析视频信息 |
| POST | /api/download | 服务端代理下载视频 |
| POST | /api/direct-url | 获取视频直链 |
| GET | /api/proxy/thumbnail | 代理缩略图（绕过防盗链） |

## 技术亮点

1. **平台路由**: 自动识别抖音链接走专用模块，其他走 yt-dlp
2. **防盗链处理**: 缩略图和视频均通过后端代理，解决浏览器跨域和 Referer 限制
3. **抖音 WAF 破解**: 自动解决抖音 sha256 反爬验证挑战
4. **ffmpeg 集成**: 通过 imageio-ffmpeg 自动下载，支持视频+音频流合并
5. **H.264 自动转码**: 检测 HEVC/H.265 编码自动转换为 H.264，确保手机微信兼容

## 后续扩展方向

- 字幕下载与翻译
- AI 视频内容总结
- 下载进度实时推送（WebSocket）
- 批量下载
- Docker 一键部署

## 免责声明

本工具仅供学习交流使用，请尊重视频版权，勿用于商业用途。下载内容的版权归原作者所有。
