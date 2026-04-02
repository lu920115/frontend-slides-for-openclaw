---
name: frontend-slides
description: 创建精美的 HTML 演示文稿，支持从零开始创建或将 PowerPoint 转换为网页幻灯片。使用视觉预览让用户选择喜欢的风格，无需设计经验。
triggers:
  - "/frontend-slides"
  - "创建幻灯片"
  - "做演示文稿"
  - "转换 PPT"
  - "PPT 转网页"
  - "frontend slides"
  - "create presentation"
  - "convert powerpoint"
---

# Frontend Slides - OpenClaw 技能

为陆哥创建零依赖、动画丰富的 HTML 演示文稿，完全在浏览器中运行。

## 核心原则

1. **零依赖** - 单个 HTML 文件，内联 CSS/JS，无需 npm、构建工具
2. **视觉化选择** - 生成视觉预览让用户选择，而非抽象描述
3. **独特设计** - 避免通用"AI 风格"，每个演示文稿都感觉定制
4. **视口适配（必须）** - 每张幻灯片必须精确适配 100vh，永不滚动

## 触发场景

陆哥说以下内容时触发此技能：
- "帮我做个幻灯片"
- "创建演示文稿"
- "把 PPT 转成网页"
- "我要做个 pitch deck"
- "/frontend-slides"

## 工作流程

### 阶段 0：检测模式

判断陆哥想要什么：
- **模式 A：新建演示文稿** - 从零创建 → 进入阶段 1
- **模式 B：PPT 转换** - 转换 .pptx 文件 → 进入阶段 4
- **模式 C：增强** - 改进现有 HTML → 读取并增强

### 阶段 1：内容发现（新建演示文稿）

**一次性问完所有问题**（用单条消息列出）：

```
陆哥，我来帮你创建演示文稿！需要确认几个问题：

1️⃣ **用途**：这个演示文稿是用来做什么的？
   - 创业融资路演
   - 教学教程
   - 会议演讲
   - 内部分享

2️⃣ **长度**：大约需要多少张幻灯片？
   - 短小精悍（5-10 张）
   - 中等长度（10-20 张）
   - 详细内容（20+ 张）

3️⃣ **内容准备**：内容准备好了吗？
   - 全部内容已就绪
   - 有粗略笔记
   - 只有主题，需要帮忙构思

4️⃣ **在线编辑**：需要在浏览器中直接编辑文字吗？
   - 需要（推荐）- 可以点击文字直接编辑，自动保存到本地
   - 不需要 - 仅展示用，文件更小

5️⃣ **图片素材**：有图片/Logo 要放入幻灯片吗？
   - 有，我提供图片文件夹路径
   - 没有，用 CSS 生成的视觉效果就好
```

根据陆哥的回答继续下一步。

### 阶段 2：风格发现

**这是"视觉化选择"阶段** - 大多数人无法用语言描述设计偏好。

#### 步骤 2.1：情绪选择

问陆哥（单选）：
```
希望观众有什么感受？（可选 1-2 个）

💼 **专业可信** - 专业、值得信赖
⚡ **活力创新** - 大胆、前卫
🧘 **冷静专注** - 清晰、沉稳
✨ **感动启发** - 情感化、令人难忘
```

#### 步骤 2.2：生成 3 个风格预览

根据情绪选择，生成 3 个不同的单页 HTML 预览，展示字体、颜色、动画和整体美学。

参考 `STYLE_PRESETS.md` 中的预设：

| 情绪 | 推荐预设 |
|------|----------|
| 专业可信 | Bold Signal, Electric Studio, Dark Botanical |
| 活力创新 | Creative Voltage, Neon Cyber, Split Pastel |
| 冷静专注 | Notebook Tabs, Paper & Ink, Swiss Modern |
| 感动启发 | Dark Botanical, Vintage Editorial, Pastel Geometry |

保存预览到 `~/.openclaw/workspace/presentations/previews/`（style-a.html, style-b.html, style-c.html）

用 `open` 命令自动在浏览器中打开每个预览给陆哥看。

#### 步骤 2.3：陆哥选择

问陆哥喜欢哪个风格，或者是否要混合元素。

### 阶段 3：生成演示文稿

使用阶段 1 的内容和阶段 2 的风格生成完整演示文稿。

**生成前读取这些支持文件：**
- `html-template.md` - HTML 架构和 JS 功能
- `viewport-base.css` - 必须的 CSS（完整包含）
- `animation-patterns.md` - 动画参考

**关键要求：**
- 单个自包含 HTML 文件，所有 CSS/JS 内联
- 包含 `viewport-base.css` 的完整内容
- 使用 Fontshare 或 Google Fonts - 永不用系统字体
- 添加详细注释说明每个部分
- 每个章节需要清晰的 `/* === SECTION NAME === */` 注释块

保存位置：`~/.openclaw/workspace/presentations/[名称]-[日期].html`

### 阶段 4：PPT 转换

转换 PowerPoint 文件时：

1. **提取内容** - 运行 `python scripts/extract-pptx.py <输入.pptx> <输出目录>`
2. **确认内容** - 向陆哥展示提取的幻灯片标题、内容摘要和图片数量
3. **风格选择** - 进入阶段 2 进行风格发现
4. **生成 HTML** - 转换为选择的风格，保留所有文字、图片、幻灯片顺序和演讲者备注

### 阶段 5：交付

1. **清理** - 删除预览文件
2. **打开** - 用 `open [文件名].html` 在浏览器中打开
3. **总结** - 告诉陆哥：
   - 文件位置和风格名称、幻灯片数量
   - 导航方式：方向键、空格键、滚动/滑动、点击导航点
   - 自定义方法：`:root` CSS 变量改颜色，font link 改字体，`.reveal` 类改动画
   - 如果启用了在线编辑：悬停左上角或按 E 进入编辑模式，点击文字编辑，Ctrl+S 保存

### 阶段 6：分享与导出（可选）

交付后问陆哥：
```
需要分享这个演示文稿吗？我可以：
- 🌐 部署到网址 - 生成可分享的链接，任何设备都能访问
- 📄 导出为 PDF - 通用格式，适合邮件、打印
- ✅ 两个都要
- ❌ 不用了
```

#### 6A：部署到网址（Vercel）

如果陆哥选择部署：

1. **检查 Vercel CLI** - 运行 `npx vercel --version`
2. **检查登录状态** - 运行 `npx vercel whoami`
3. **部署** - 运行 `bash scripts/deploy.sh <演示文稿路径>`
4. **分享网址** - 告诉陆哥链接和使用方法

#### 6B：导出为 PDF

如果陆哥选择导出 PDF：

1. **运行导出脚本** - `bash scripts/export-pdf.sh <HTML 路径> [输出.pdf]`
2. **说明** - 动画不会保留（静态快照），但视觉效果依然出色
3. **交付** - 脚本会自动打开 PDF，告诉陆哥文件位置

## 支持文件

| 文件 | 用途 | 何时读取 |
|------|------|----------|
| `STYLE_PRESETS.md` | 12 个精选视觉预设 | 阶段 2（风格选择） |
| `viewport-base.css` | 必须的响应式 CSS | 阶段 3（生成） |
| `html-template.md` | HTML 结构和 JS 功能 | 阶段 3（生成） |
| `animation-patterns.md` | CSS/JS 动画参考 | 阶段 3（生成） |
| `scripts/extract-pptx.py` | PPT 内容提取 | 阶段 4（转换） |
| `scripts/deploy.sh` | 部署到 Vercel | 阶段 6（分享） |
| `scripts/export-pdf.sh` | 导出为 PDF | 阶段 6（分享） |

## 设计注意事项

### 视口适配规则（必须遵守）

- 每个 `.slide` 必须有 `height: 100vh; height: 100dvh; overflow: hidden;`
- 所有字体大小和间距必须使用 `clamp(min, preferred, max)` - 永不用固定 px/rem
- 内容容器需要 `max-height` 约束
- 图片：`max-height: min(50vh, 400px)`
- 断点要求：700px, 600px, 500px
- 包含 `prefers-reduced-motion` 支持
- 永不在 CSS 函数前直接加负号（`-clamp()` 会被浏览器忽略）- 使用 `calc(-1 * clamp(...))`

### 每张幻灯片内容密度限制

| 幻灯片类型 | 最大内容 |
|------------|----------|
| 标题页 | 1 个标题 + 1 个副标题 + 可选标语 |
| 内容页 | 1 个标题 + 4-6 个要点 或 1 个标题 + 2 段文字 |
| 特性网格 | 1 个标题 + 最多 6 个卡片（2x3 或 3x2） |
| 代码页 | 1 个标题 + 8-10 行代码 |
| 引用页 | 1 个引用（最多 3 行）+ 署名 |
| 图片页 | 1 个标题 + 1 张图片（最大 60vh 高度） |

**内容超出限制？分成多张幻灯片。永不堆砌，永不滚动。**

### 避免通用 AI 风格

- 过度使用的字体（Inter, Roboto, Arial, 系统字体）
- 陈词滥调的配色（特别是白色背景上的紫色渐变）
- 可预测的布局和组件模式
- 缺乏个性的模板化设计

## 文件位置

| 类型 | 位置 |
|------|------|
| **技能目录** | `~/.openclaw/workspace/skills/skills/frontend-slides/` |
| **演示文稿输出** | `~/.openclaw/workspace/presentations/` |
| **预览文件** | `~/.openclaw/workspace/presentations/previews/` |
| **脚本** | `~/.openclaw/workspace/skills/skills/frontend-slides/scripts/` |

## 使用示例

### 创建新演示文稿

```
/frontend-slides

陆哥：我想做个创业融资路演
→ 进入阶段 1：内容发现
→ 进入阶段 2：风格发现（生成 3 个预览）
→ 进入阶段 3：生成演示文稿
→ 进入阶段 5：交付
→ 进入阶段 6：询问是否需要分享/导出
```

### 转换 PPT

```
/frontend-slides

陆哥：把 ~/Documents/融资路演.pptx 转成网页
→ 进入阶段 4：PPT 转换
→ 提取内容并确认
→ 进入阶段 2：风格发现
→ 进入阶段 3：生成演示文稿
→ 进入阶段 5：交付
```

## 依赖检查

使用前检查：
- ✅ Python（PPT 转换需要 `python-pptx` 库）
- ✅ Node.js（部署和 PDF 导出需要）
- ✅ 浏览器（查看演示文稿）

---

**技能目标：** 让陆哥无需设计经验也能创建精美的演示文稿，通过视觉化选择而非抽象描述来发现喜欢的风格。
