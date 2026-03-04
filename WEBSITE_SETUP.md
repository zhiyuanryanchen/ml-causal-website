# 课程网站设置指南

## 概述

课程网站已使用 Quarto 创建，可以部署到 GitHub Pages。

## 文件结构

```
.
├── _quarto.yml           # Quarto 网站配置
├── index.qmd             # 首页
├── syllabus.qmd          # 课程大纲
├── resources.qmd         # 学习资源
├── styles.css            # 自定义样式
├── docs/                 # 生成的网站文件
│   ├── index.html
│   ├── syllabus.html
│   ├── resources.html
│   └── Quarto/
│       ├── lecture01_students.html
│       └── lecture01_notes.html
└── .github/workflows/
    └── publish.yml       # GitHub Actions 自动部署
```

## 设置步骤

### 1. 创建 GitHub 仓库

在 GitHub 上创建一个新仓库，建议名称：`ml-causal-inference` 或 `causal-inference-course`

### 2. 更新远程仓库地址

```bash
# 查看当前远程
git remote -v

# 添加新的远程（用你的用户名和仓库名替换）
git remote add course https://github.com/YOUR_USERNAME/ml-causal-inference.git

# 或者替换现有的 origin
# git remote set-url origin https://github.com/YOUR_USERNAME/ml-causal-inference.git
```

### 3. 推送代码到 GitHub

```bash
# 添加新文件
git add _quarto.yml index.qmd syllabus.qmd resources.qmd styles.css
git add .github/workflows/publish.yml
git add docs/
git add WEBSITE_SETUP.md

# 提交更改
git commit -m "Add course website"

# 推送到 GitHub
git push course main
# 或
git push origin main
```

### 4. 启用 GitHub Pages

1. 打开 GitHub 仓库页面
2. 进入 Settings → Pages
3. Source 选择 "Deploy from a branch"
4. Branch 选择 "gh-pages" → "/ (root)"
5. 点击 Save

### 5. 自动部署

网站配置已包含 GitHub Actions 工作流 (`.github/workflows/publish.yml`)，每次推送到 `main` 分支时会自动：
- 渲染 Quarto 网站
- 部署到 `gh-pages` 分支
- 更新 GitHub Pages

## 更新网站内容

### 添加新讲义

1. 创建新的 HTML 文件（如 `lecture02_students.html`）
2. 复制到 `Quarto/` 目录
3. 更新 `_quarto.yml` 中的导航菜单
4. 运行 `quarto render` 重新渲染
5. 提交并推送更改

### 修改现有页面

```bash
# 编辑文件
# - index.qmd (首页)
# - syllabus.qmd (课程大纲)
# - resources.qmd (学习资源)

# 渲染网站
quarto render

# 提交并推送
git add .
git commit -m "Update website content"
git push
```

## 本地预览

```bash
# 在网站根目录运行
quarto preview

# 或直接在浏览器打开
docs/index.html
```

## 网站地址

启用 GitHub Pages 后，网站将可通过以下地址访问：

```
https://YOUR_USERNAME.github.io/ml-causal-inference
```

## 自定义域名（可选）

1. 在 `docs/` 目录下创建 `CNAME` 文件
2. 写入自定义域名（如 `causalml.youruniversity.edu.cn`）
3. 在 DNS 提供商处配置 CNAME 记录指向 `YOUR_USERNAME.github.io`

## 故障排除

### 网站未更新
- 检查 GitHub Actions 是否运行成功
- 确认 `gh-pages` 分支已创建
- 检查 GitHub Pages 设置中的分支配置

### 样式丢失
- 确保 `styles.css` 已提交
- 检查 `_quarto.yml` 中是否正确引用了 CSS

### 链接失效
- 检查 `_quarto.yml` 中的文件路径
- 确保 `Quarto/` 目录下的讲义文件已复制到 `docs/Quarto/`

## 更多信息

- [Quarto 网站文档](https://quarto.org/docs/websites/)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [Quarto + GitHub Pages 教程](https://quarto.org/docs/publishing/github-pages.html)
