# Frontend Slides for OpenClaw

为 OpenClaw 打造的 HTML 演示文稿生成技能，帮助非设计师创建精美、动画丰富的网页幻灯片。

## ✨ 特性

- 🎨 **视觉化风格选择** - 生成视觉预览让用户选择，而非抽象描述
- 📱 **零依赖** - 单个 HTML 文件，内联 CSS/JS，无需构建工具
- 🖼️ **PPT 转换** - 支持将 PowerPoint 文件转换为网页幻灯片
- ✏️ **在线编辑** - 可在浏览器中直接编辑文字和替换图片
- 🚀 **一键部署** - 支持部署到 Vercel 或导出为 PDF
- 🎯 **视口适配** - 每张幻灯片精确适配 100vh，永不滚动

## 📦 安装

### 方法一：克隆到 OpenClaw Skills 目录

```bash
# 克隆到 OpenClaw skills 目录
git clone https://github.com/lu920115/frontend-slides-for-openclaw.git ~/.openclaw/workspace/skills/skills/frontend-slides
```

### 方法二：手动复制

```bash
# 创建技能目录
mkdir -p ~/.openclaw/workspace/skills/skills/frontend-slides/scripts

# 复制技能文件
cp SKILL.md STYLE_PRESETS.md viewport-base.css html-template.md animation-patterns.md ~/.openclaw/workspace/skills/skills/frontend-slides/
cp scripts/* ~/.openclaw/workspace/skills/skills/frontend-slides/scripts/
```

## 🚀 使用方法

在 OpenClaw 中触发技能：

### 触发命令
- `/frontend-slides`
- "帮我做个幻灯片"
- "创建演示文稿"
- "把 PPT 转成网页"
- "frontend slides"

### 工作流程

1. **内容发现** - 一次性确认用途、长度、内容准备情况
2. **风格发现** - 根据偏好生成 3 个视觉预览供选择
3. **生成演示文稿** - 创建完整的 HTML 演示文稿
4. **交付与分享** - 可选择部署到网址或导出为 PDF

### 使用示例

```
/frontend-slides

我想做个创业融资路演
→ 技能会询问内容、风格偏好
→ 生成 3 个风格预览
→ 选择后生成完整演示文稿
```

### PPT 转换

```
/frontend-slides

把 ~/Documents/融资路演.pptx 转成网页
→ 提取 PPT 内容
→ 确认提取结果
→ 选择风格并生成
```

## 📁 文件结构

```
frontend-slides/
├── SKILL.md              # 技能主文件（OpenClaw 适配版）
├── README.md             # 使用说明
├── STYLE_PRESETS.md      # 12 种视觉风格预设
├── viewport-base.css     # 视口适配基础 CSS
├── html-template.md      # HTML 模板架构
├── animation-patterns.md # 动画模式参考
└── scripts/
    ├── extract-pptx.py   # PPT 内容提取脚本
    ├── deploy.sh         # 部署到 Vercel
    └── export-pdf.sh     # 导出为 PDF
```

## 🎨 支持的风格

### 深色主题
- **Bold Signal** - 自信、大胆、高影响力
- **Electric Studio** - 专业、简洁、高对比度
- **Creative Voltage** - 活力、创意、复古现代
- **Dark Botanical** - 优雅、精致、艺术感

### 浅色主题
- **Notebook Tabs** - 编辑风格、有组织感
- **Pastel Geometry** - 友好、现代、亲和力
- **Split Pastel** - 活泼、现代、创意
- **Vintage Editorial** - 个性、编辑风格

### 特色主题
- **Neon Cyber** - 未来感、科技感
- **Terminal Green** - 开发者风格、黑客美学
- **Swiss Modern** - 极简、包豪斯风格
- **Paper & Ink** - 文学、编辑风格

## 📄 输出位置

演示文稿保存到：`~/.openclaw/workspace/presentations/`

## ⚙️ 依赖要求

### 基础功能
- ✅ OpenClaw 运行环境

### PPT 转换（可选）
```bash
pip3 install python-pptx
```

### 部署到 Vercel（可选）
```bash
# 需要 Node.js
brew install node
npx vercel login
```

### 导出 PDF（可选）
```bash
# 脚本会自动安装 Playwright
```

## 🛠️ 开发说明

本技能基于 [frontend-slides](https://github.com/lu920115/frontend-slides) 项目改造，针对 OpenClaw 平台进行了适配：

- 修改触发器为 OpenClaw 命令格式
- 调整交互方式为消息对话
- 优化文件路径为 OpenClaw 工作区
- 添加中文支持和本地化

## 📝 更新日志

### v1.0.0 (2026-04-02)
- ✅ 初始版本发布
- ✅ OpenClaw 平台适配
- ✅ 支持 PPT 转换
- ✅ 12 种视觉风格
- ✅ 在线编辑功能
- ✅ 部署和 PDF 导出

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

MIT License - 自由使用、修改和分享

## 👨‍💻 作者

- GitHub: [@lu920115](https://github.com/lu920115)
- 基于 [frontend-slides](https://github.com/zarazhangrui/frontend-slides) 项目改造

## 🙏 致谢

感谢原项目作者的出色工作，本技能在其基础上针对 OpenClaw 平台进行了适配和优化。

---

**让每个人都能轻松创建精美的演示文稿！** 🎉
