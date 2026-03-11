# 博客系统搭建踩坑总结

> 日期：2026-03-11
> 目的：避免重复犯错

---

## 踩坑列表

### 1. SD WebUI 安装失败 ❌

**问题：** 尝试手动安装 WebUI 依赖，编译 CLIP 失败

**原因：** 
- Windows 编译环境缺失
- Python 版本不兼容
- 依赖链过于复杂

**解决方案：** 
- 使用预编译版或 diffusers Python 脚本

---

### 2. 模型选择错误 ❌

**问题：** 想用 Qwen-Image（20B）但显存不够

**原因：** 没提前了解模型大小

**解决方案：** 
- 6GB 显存 → 用 SDXL-base-1.0 或 SDXL-Lightning

---

### 3. Hugo 安装失败 ❌

**问题：** winget 安装成功但命令找不到

**原因：** 
- PATH 没刷新
- 终端需要重启

**解决方案：**
- 用 Python 生成静态 HTML 替代 Hugo

---

### 4. GitHub Pages 404 ❌

**问题：** 博客上线后 404

**原因：** 
- main 分支没有静态文件
- 源码不能直接作为 Pages

**解决方案：**
- 用 gh-pages 分支存储静态文件

---

### 5. 链接路径错误 ❌

**问题：** 子页面链接全部 404

**原因：** 
- 链接用 `/diary/` 而不是 `/blog/diary/`

**解决方案：**
- 所有内部链接加 `/blog/` 前缀

---

### 6. 空链接 ❌

**问题：** 好文分享有无效链接

**原因：** 
- 用示例链接没替换

**解决方案：**
- 添加真实内容或删除空链接

---

## 正确流程（推荐）

### 1. 生成图片（可选）
```python
# 用 diffusers + SDXL
pipe = StableDiffusionXLPipeline.from_pretrained(
    "stabilityai/stable-diffusion-xl-base-1.0",
    torch_dtype=torch.float16
)
image = pipe(prompt).images[0]
```

### 2. 生成静态 HTML
```python
# 保持链接用 /blog/ 前缀
html = html.replace('href="/', 'href="/blog/')
```

### 3. 推送到 gh-pages
```powershell
git checkout -b gh-pages
git add .
git commit -m "Update"
git push origin gh-pages
```

### 4. 配置 GitHub Pages
- Settings → Pages
- Branch: gh-pages
- Save

---

## 经验总结

1. **先学习再动手** - 搜索技能、读文档
2. **简单方案优先** - Python 脚本 > 复杂框架
3. **验证每步** - 及时检查输出
4. **备份配置** - 保留工作配置
