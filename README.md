# 🧩 JSONL Format Editor

> 一个纯静态、浏览器端运行的 JSONL 编辑器，支持本地导入、记录检索、原始 JSON 编辑、树形字段编辑、模板复用与 JSONL 导出。

---

## 📌 项目简介

JSONL Format Editor 是一个面向 JSONL / JSON 数据整理场景的轻量级网页工具。项目无需后端服务，直接在浏览器中解析、编辑和导出文件，适合用于标注数据、评测集、提示词样本、训练样本和结构化记录的快速清洗。

所有文件处理都发生在用户本地浏览器中，数据不会上传到服务器，适合处理需要离线编辑或临时整理的 JSONL 文件。

---

## ✨ 核心能力

- 📂 本地导入 `.jsonl` / `.json` / 文本文件
- 🔎 按 `id`、文本内容或字段内容搜索记录
- 🧾 原始 JSON 编辑区，支持格式化与错误定位
- 🌳 树形 JSON 编辑器，支持对象、数组、文本、数字、布尔值和空值
- ↶ 撤销 / 重做，支持快捷键操作
- ➕ 新增、删除、保存当前记录
- 🧩 模板管理，支持从已有 JSON 或粘贴 JSON 中提取模板
- 📤 导入 / 导出模板配置
- 💾 导出编辑后的 JSONL 文件
- 🛡️ 纯前端运行，不依赖 Python、Node 服务或数据库

---

## 🏗️ 工作流程

```text
Local JSONL / JSON File
    ↓
Browser FileReader
    ↓
Record List + Search
    ↓
Raw JSON Editor  ←→  Tree Editor
    ↓
Template / Undo / Redo
    ↓
Export edited JSONL
```

---

## 📂 项目结构

```text
.
├── index.html          # GitHub Pages 入口，自动跳转到 web/
├── web/
│   ├── index.html      # JSONL 编辑器主页面，包含样式与脚本
│   └── .nojekyll       # GitHub Pages 静态部署配置
├── .nojekyll
├── .gitignore
└── README.md
```

---

## ⚡ 快速开始

### 1️⃣ 在线访问

如果启用了 GitHub Pages，可直接访问：

```text
https://ldliu0221.github.io/Jsonl-Format-Editor/
```

### 2️⃣ 本地打开

直接双击打开：

```text
web/index.html
```

或使用任意静态服务器：

```bash
python -m http.server 8000
```

然后访问：

```text
http://127.0.0.1:8000/web/
```

---

## 🧪 使用方式

### 📥 导入文件

点击 `选择文件`，选择 `.jsonl`、`.json` 或文本文件。

JSONL 文件示例：

```jsonl
{"id":"case-001","input":"检查所见文本","output":"诊断意见文本"}
{"id":"case-002","input":"另一条记录","label":"normal"}
```

### ✍️ 编辑记录

- 左侧列表用于切换记录和搜索内容。
- 中间区域可直接编辑原始 JSON，并使用 `格式化` 或 `应用原始 JSON`。
- 右侧树形视图可按字段编辑对象、数组和值。
- 修改后点击 `保存当前记录`。

### 🧩 使用模板

在 `模板管理` 中可以：

- 从已有 JSON 提取模板
- 从粘贴的 JSON 提取模板
- 保存 3 组常用模板
- 导入 / 导出模板配置
- 新增记录时按模板生成空字段

### 📤 导出 JSONL

编辑完成后点击 `导出 JSONL`，浏览器会下载编辑后的 `.jsonl` 文件。

---

## 🔐 隐私说明

本工具为纯静态网页应用：

- 不上传文件
- 不请求后端接口
- 不保存数据到服务器
- 草稿和模板仅保存在浏览器本地存储中

如果处理敏感数据，建议在可信浏览器环境中离线使用，并在完成后按需清理浏览器本地存储。

---

## 🚀 部署到 GitHub Pages

仓库已包含根目录 `index.html`，会自动跳转到 `web/`。

部署步骤：

1. 打开仓库 `Settings`
2. 进入 `Pages`
3. Source 选择 `Deploy from a branch`
4. Branch 选择 `main`
5. Folder 选择 `/ (root)`
6. 保存后等待 GitHub Pages 完成部署

---

## 🧠 技术亮点

- 零后端依赖，适合 GitHub Pages / Cloudflare Pages 静态托管
- 使用浏览器 `FileReader` 读取本地文件
- 使用 `Blob` 和下载链接导出编辑结果
- 同步维护原始 JSON 文本与树形编辑状态
- JSON 解析错误可定位行列，便于快速修正
- 模板和草稿保存在 `localStorage`

---

## ⭐ 项目总结

JSONL Format Editor 是一个小而实用的 JSONL 数据整理工具，适合在数据标注、模型评测、样本构造和结构化文本清洗中快速使用。它不需要部署服务，也不接触服务器端数据，打开网页即可完成本地编辑与导出。
