# JSONL 编辑器静态网页版部署

静态网页版位于 `web/` 目录。

## 本地打开

直接双击：

```text
web/index.html
```

也可以用任意静态服务器打开 `web/` 目录。

## 部署到 GitHub Pages

1. 新建 GitHub 仓库。
2. 上传 `web/` 目录里的文件。
3. 进入仓库 `Settings -> Pages`。
4. 选择部署分支和目录。
5. 打开 GitHub Pages 生成的网址。

## 部署到 Cloudflare Pages

1. 新建 Cloudflare Pages 项目。
2. 上传 `web/` 目录，或连接 GitHub 仓库。
3. 不需要构建命令。
4. 输出目录按上传方式填写 `/` 或 `web`。

## 隐私说明

这个版本不需要 Python 服务。JSONL 文件只在用户自己的浏览器里解析、编辑和导出，不会上传到服务器。
