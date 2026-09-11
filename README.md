# Golden Quote — 金句海报生成器

> 把一段话变成一张可分享的精致海报。

[![GitHub](https://img.shields.io/badge/owner-ylzbl-blue)](https://github.com/ylzbl)
[![Pure HTML](https://img.shields.io/badge/pure-HTML%2FCSS%2FJS-orange)]()
[![html2canvas](https://img.shields.io/badge/export-html2canvas-red)]()

---

## 这是什么

Golden Quote 是一个**纯前端的金句海报生成器**，输入一段文字 + 一张背景图，就能生成带有引号装饰、字体排版、配色主题的"金句卡片"，一键导出为 PNG。

典型使用场景：

- 把每天读到的精彩段落做成卡片存档
- 公众号 / 小红书配图
- 朋友圈分享卡片
- 知识管理工具的卡片素材源

## 功能特性

### 排版
- 内置 **Smiley Sans（得意黑）** 作为标题字体，倾斜 + 加粗，视觉冲击力强
- 内置 **Alibaba PuHuiTi（阿里巴巴普惠体）** 作为正文字体
- 字体本地化加载（仓库自带 woff / woff2），不依赖外网
- 主标题 / 引文 / 署名三层结构，自动适配

### 主题
- 主题色系通过 CSS 变量管理（背景、主色、引文卡片底色、文字主色）
- 预设深色金色调（`#1A1813` + `#F3B64A`），可自由切换
- 海报主色调与 UI 强调色联动，所见即所得

### 背景
- 支持上传本地图片作为背景
- 引文卡片半透明叠加在背景上，保证文字可读性
- 背景图与主题色混合，统一视觉调性

### 导出
- 基于 [html2canvas](https://html2canvas.hertzen.com/) 1.4.1 实现客户端导出
- 输出 PNG，无服务器依赖
- 导出尺寸跟随预览画布，可调整

### 配置持久化
- 完整海报配置（主题、文字、背景图 base64）可保存为 JSON
- 仓库自带 `poster_settings.json` 和 `poster_settings-2604.json` 两份示例配置
- 直接拖入 JSON 文件即可还原海报状态

## 使用方法

### 快速开始
1. 下载本仓库（含字体文件，约 9MB）
2. 双击 `index.html` 在浏览器中打开
3. 在左侧控制面板填入金句文字、署名
4. 上传背景图（可选）
5. 调整主题色、字号、间距
6. 点击「下载 PNG」导出

### 部署
- **本地使用**：直接双击 `index.html`
- **GitHub Pages**：推送到仓库后启用 Pages，访问 `https://<user>.github.io/golden-quote/`
- **Cloudflare Pages**：直接连接 GitHub 仓库即可部署

## 文件结构

```
golden-quote/
├── index.html                       # 单文件应用（HTML + CSS + JS 内联）
├── html2canvas.min.js               # 导出依赖（本地化）
├── SmileySans-Oblique.ttf.woff2     # 得意黑（标题字体）
├── AlibabaPuHuiTi-3-55-Regular.woff # 阿里巴巴普惠体（正文字体）
├── poster_settings.json             # 默认海报配置示例
└── poster_settings-2604.json        # 备用海报配置示例
```

## 注意事项

1. 字体文件较大（woff2 约 2MB），首次加载会有延迟，建议部署到 CDN
2. `poster_settings.json` 中包含背景图的 base64 编码，文件可能较大
3. html2canvas 对部分 CSS 特性支持不完整（如 `backdrop-filter`），导出效果可能与预览略有差异
4. 大尺寸背景图导出时可能卡顿，建议先压缩到 1920px 宽以内

## Roadmap

- [ ] 更多预设主题（极简白、纸张感、杂志风）
- [ ] 支持多段引文 + 头像组合
- [ ] 支持中英双语混排
- [ ] 模板库（节日、生日、励志、商务）
- [ ] 一键分享到社交媒体

## License

- 代码：MIT
- 字体：遵循原字体授权（Smiley Sans / Alibaba PuHuiTi 均为免费可商用）
