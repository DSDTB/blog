# 博客发布技能

> 用于发布文章到 GitHub Pages 静态博客

## 触发条件
当用户说"发布博客"、"更新博客"、"添加文章"时使用

## 工作流程

### 1. 内容准备
- 编写 Markdown 或 HTML 内容
- 准备好配图（用 SDXL 生成）
- 检查敏感信息

### 2. 静态文件生成
- 用 Python 脚本生成 HTML
- 确保链接使用 `/blog/` 前缀
- 复制静态资源（图片等）

### 3. Git 推送到 gh-pages 分支
```powershell
# 进入 public 目录
git add .
git commit -m "Update blog"
git push origin gh-pages
```

### 4. 等待部署
- GitHub Pages 自动部署
- 约 1-2 分钟后生效

## 注意事项
- 链接必须加 `/blog/` 前缀
- 不要有空链接
- 用 gh-pages 分支（不是 main）
