# 网站维护指南

## 网站结构

```
bichengdong.github.io/
├── index.md                 # 中文首页
├── cv.md                    # 中文简历
├── publications.md          # 中文论文
├── teaching.md              # 中文教学
├── en/                      # 英文页面
│   ├── index.md
│   ├── cv.md
│   ├── publications.md
│   └── teaching.md
├── assets/images/           # 图片资源
│   ├── front_image.png      # 首页头像
│   ├── publications-wordcloud.jpg
│   ├── google-scholar.png
│   └── researchgate.png
├── _includes/               # 页面组件
│   ├── header.html          # 导航栏
│   ├── footer.html          # 页脚
│   └── language-switcher.html
├── css/main.scss            # 样式文件
└── _config.yml              # 网站配置
```

---

## 页面 Front Matter 说明

每个 `.md` 文件开头必须包含 front matter（YAML 格式）：

```yaml
---
layout: page
title: 页面标题
lang: zh          # 中文页面用 zh，英文页面用 en
permalink: /en/cv/  # 英文页面需要设置永久链接
---
```

**重要：** `lang` 字段决定导航栏显示中文还是英文菜单。

---

## 常见修改操作

### 1. 添加新论文

编辑 `publications.md`（中文）和 `en/publications.md`（英文），在相应年份下添加：

```html
<div class="pub-entry"><strong>Dong, B.-C.</strong>, 其他作者... (年份). 论文标题. <strong>期刊名</strong>, 卷号, 页码. <a href="https://doi.org/xxx" target="_blank">DOI: xxx</a></div>
```

**格式说明：**

- `<strong>Dong, B.-C.</strong>` — 第一作者加粗
- `<strong>Dong, B.-C.*</strong>` — 通讯作者加粗并标 `*`
- `<em>物种名</em>` — 物种名斜体

### 2. 更新论文统计

修改页面顶部的统计文字：

```html
<p style="font-size: 0.95em; color: #555;">共发表SCI论文23篇（第一作者15篇，通讯作者8篇）。</p>
```

### 3. 修改 CV 信息

编辑 `cv.md` 和 `en/cv.md`，使用 Markdown 表格格式：

```markdown
| 时间 | 职位 | 单位 |
|------|------|------|
| 2020 – 至今 | 副教授 | 北京林业大学 |
```

### 4. 更换头像

将新图片放入 `assets/images/`，然后修改 `index.md` 和 `en/index.md` 中的图片路径：

```html
<img src="/assets/images/新图片名.jpg" alt="Bi-Cheng Dong" />
```

### 5. 添加学术兼职

在 CV 页面的学术兼职部分添加：

```markdown
- *期刊名* 职位（年份范围）
```

---

## 提交更改

### 方法一：命令行

```bash
cd bichengdong.github.io
git add .
git commit -m "描述你的修改"
git push
```

### 方法二：GitHub 网页

1. 在 GitHub 仓库页面直接编辑文件
2. 点击 "Commit changes"

---

## 注意事项

1. **中英文同步**：修改中文页面后，记得同步修改对应的英文页面
2. **lang 字段**：确保每个页面都有正确的 `lang: zh` 或 `lang: en`
3. **图片大小**：建议图片压缩后上传，避免加载过慢
4. **本地预览**：

```bash
bundle exec jekyll serve
# 访问 http://localhost:4000
```

---

## 文件对应关系

| 中文              | 英文                 | 说明  |
| --------------- | ------------------ | --- |
| index.md        | en/index.md        | 首页  |
| cv.md           | en/cv.md           | 简历  |
| publications.md | en/publications.md | 论文  |
| teaching.md     | en/teaching.md     | 教学  |

---

## 联系方式修改

如需修改邮箱、电话等，编辑 `cv.md` 和 `en/cv.md` 中的联系方式表格。

---

*最后更新：2025年*
