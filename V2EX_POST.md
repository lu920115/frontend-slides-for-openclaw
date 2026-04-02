标题：我为 OpenClaw 做了个 PPT 转网页的技能，欢迎大家试用

正文：

大家好，我是一名三甲医院医生，平时需要做很多教学汇报 PPT。

最近用 OpenClaw 开发了一个技能，可以一键生成精美的 HTML 演示文稿，现在开源给大家试用！

**GitHub:** https://github.com/lu920115/frontend-slides-for-openclaw

---

## 🎯 解决什么问题

1. **公用电脑兼容性问题** - 单个 HTML 文件，任何电脑有浏览器就能用
2. **临时修改内容** - 在浏览器里直接编辑文字、替换图片
3. **美化耗时** - AI 自动生成，12 种风格可选，审美在线
4. **PPT 转换** - 现有 PPT 直接转网页，保留所有图片和内容

---

## ✨ 核心功能

- **视觉化风格选择** - 生成 3 个预览让你选，而不是抽象描述
- **PPT 转换** - 支持提取 PowerPoint 内容并转换
- **在线编辑** - 点击文字就能改，图片可以替换/删除
- **一键部署** - 可部署到 Vercel 生成链接，或导出 PDF
- **视口适配** - 每张幻灯片精确适配屏幕，永不滚动

---

## 🚀 使用方式

```bash
# 安装
git clone https://github.com/lu920115/frontend-slides-for-openclaw.git ~/.openclaw/workspace/skills/skills/frontend-slides

# 在 OpenClaw 中使用
/frontend-slides
```

---

## 📸 效果

（此处可添加截图或 GIF）

风格包括：Bold Signal、Electric Studio、Notebook Tabs、Paper & Ink 等 12 种。

---

## 💡 技术实现

- 基于 frontend-slides 项目改造
- 针对 OpenClaw 适配了交互方式
- 图片内嵌 base64，单文件即可使用
- 纯前端，无后端依赖

---

## 🙏 致谢

感谢原项目作者 [@zarazhangrui](https://github.com/zarazhangrui) 的出色工作。

---

欢迎大家试用，有问题欢迎提 issue！也欢迎分享你的使用场景～

---

**更新日志：**
- 2026-04-02: 初始发布
