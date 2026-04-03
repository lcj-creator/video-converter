[README.md](https://github.com/user-attachments/files/26451707/README.md)
# 视频格式转换工具

一个在线视频格式转换工具，支持将.dav等多种视频格式转换为MP4、AVI、MOV、WMV等格式。

## 功能特性

- ✅ 支持多种视频格式转换（.dav, .mp4, .avi, .mov, .wmv等）
- ✅ 直观的文件上传界面（支持拖拽上传）
- ✅ 实时转换进度显示
- ✅ 转换完成后提供下载链接
- ✅ 响应式设计，支持不同设备

## 技术栈

### 前端
- React + Vite
- CSS3

### 后端
- Node.js + Express
- FFmpeg (核心转换工具)
- Multer (文件上传处理)
- CORS (跨域支持)

## 安装和运行

### 前提条件

1. **Node.js** (v14.0+)
2. **FFmpeg** (必须安装，用于视频转换)

### 安装步骤

1. **克隆项目**
   ```bash
   git clone <项目地址>
   cd <项目目录>
   ```

2. **安装依赖**
   ```bash
   # 安装后端依赖
   npm install
   
   # 安装前端依赖
   cd frontend
   npm install --legacy-peer-deps
   ```

3. **构建前端**
   ```bash
   cd frontend
   npm run build
   ```

4. **启动服务器**
   ```bash
   cd ..
   node index.js
   ```

5. **访问应用**
   打开浏览器，访问 `http://localhost:3000`

## FFmpeg安装指南

### Windows
1. 下载FFmpeg：https://ffmpeg.org/download.html#build-windows
2. 解压到本地目录
3. 将FFmpeg的bin目录添加到系统环境变量PATH中
4. 验证安装：打开命令提示符，运行 `ffmpeg -version`

### macOS
1. 使用Homebrew安装：`brew install ffmpeg`
2. 验证安装：运行 `ffmpeg -version`

### Linux
1. 使用包管理器安装：
   - Ubuntu/Debian: `sudo apt install ffmpeg`
   - CentOS/RHEL: `sudo yum install ffmpeg`
2. 验证安装：运行 `ffmpeg -version`

## 使用方法

1. **上传文件**：点击或拖拽视频文件到上传区域
2. **选择目标格式**：从下拉菜单中选择要转换的目标格式
3. **开始转换**：点击"开始转换"按钮
4. **等待转换**：查看转换进度条
5. **下载结果**：转换完成后，点击"下载文件"链接获取转换后的视频

## 支持的格式

### 输入格式
- .dav (监控摄像头视频格式)
- .mp4
- .avi
- .mov
- .wmv
- 其他常见视频格式

### 输出格式
- MP4 (推荐)
- AVI
- MOV
- WMV

## 项目结构

```
├── backend/           # 后端代码目录
├── frontend/          # 前端代码目录
│   ├── src/           # 前端源码
│   ├── dist/          # 构建后的静态文件
│   ├── package.json   # 前端依赖配置
│   └── vite.config.js # Vite配置
├── uploads/           # 临时文件存储目录
├── index.js           # 后端主服务器文件
├── package.json       # 后端依赖配置
└── README.md          # 项目文档
```

## API接口

### POST /api/convert
- **功能**：上传并转换视频文件
- **参数**：
  - `file`：要转换的视频文件
  - `format`：目标格式 (mp4, avi, mov, wmv)
- **返回**：转换后的文件信息

### GET /api/download/:filename
- **功能**：下载转换后的视频文件
- **参数**：
  - `filename`：转换后的文件名
- **返回**：视频文件下载

## 常见问题

### 1. 转换失败，提示"FFmpeg未安装"
- **解决方案**：按照FFmpeg安装指南安装FFmpeg，并确保添加到系统环境变量

### 2. 转换过程中出现错误
- **可能原因**：
  - 视频文件损坏
  - FFmpeg版本不兼容
  - 系统资源不足
- **解决方案**：
  - 检查视频文件是否完整
  - 更新FFmpeg到最新版本
  - 尝试转换较小的视频文件

### 3. 下载链接无法访问
- **可能原因**：
  - 文件已被清理
  - 服务器重启
- **解决方案**：
  - 重新上传并转换视频
  - 确保服务器正常运行

## 性能优化

- **文件大小限制**：建议转换小于1GB的视频文件
- **转换速度**：转换速度取决于视频大小和系统性能
- **内存使用**：大文件转换可能需要较多内存

## 许可证

MIT License

## 贡献

欢迎提交问题和改进建议！
