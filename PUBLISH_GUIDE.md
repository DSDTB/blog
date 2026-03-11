# 博客发布优化流程

> 版本：2.0
> 日期：2026-03-11
> 基于实战经验优化

---

## 优化后的发布流程

### 步骤 1：准备内容
- 用 Python 脚本生成 HTML
- **关键：链接加 `/blog/` 前缀**
- 检查无空链接

### 步骤 2：推送到 gh-pages
```powershell
cd E:\openclaw\blog\public
git add .
git commit -m "Update blog"
git push origin gh-pages
```

### 步骤 3：验证
- 等待 2-3 分钟
- 访问 https://dsdtb.github.io/blog/

---

## 常见问题及解决方案

| 问题 | 原因 | 解决 |
|------|------|------|
| 404 | 用了 main 分支 | 用 gh-pages 分支 |
| 404 | 链接缺前缀 | 加 `/blog/` |
| 404 | 部署未完成 | 等 2-3 分钟 |
| 空链接 | 没填内容 | 删除或填真实链接 |

---

## 目录规范

- **工作目录：** `E:\openclaw\`
- **博客源码：** `E:\openclaw\blog\`
- **静态文件：** `E:\openclaw\blog\public\`
- **AI 工具：** `E:\openclaw\ai-tools\`

---

## 快速命令

### 添加新日记
```powershell
# 1. 创建 HTML 文件
# 2. 更新 index.html
# 3. 推送
cd E:\openclaw\blog\public
git add .
git commit -m "Add new post"
git push origin gh-pages
```

---

## 检查清单

发布前检查：
- [ ] 链接都有 `/blog/` 前缀
- [ ] 无空链接（删除或填内容）
- [ ] 图片路径正确
- [ ] 已推送到 gh-pages
