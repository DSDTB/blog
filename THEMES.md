# 博客皮肤系统

## 三套皮肤

### 1. Cute 可爱风（默认）
```toml
[params]
  theme_color = "#FF69B4"  # 粉色
  description = "可爱活泼风"
```
特点：粉色系、卡通图标、圆润字体

### 2. Tech 科技风
```toml
[params]
  theme_color = "#00D4FF"  # 蓝色
  description = "科技简约风"
```
特点：蓝色系、代码风格、简洁线条

### 3. Ink 水墨风
```toml
[params]
  theme_color = "#2C3E50"  # 深色
  description = "水墨古典风"
```
特点：水墨画元素、传统配色、书法字体

## 切换方式

在 config.toml 中修改：
```toml
theme = "beautifulhugo"  # 当前主题
```

或通过命令：
```
hugo server --theme=cute
```
