# Jekyll Academic Website - 安装与部署指南

本指南将帮助你在本地运行并部署本项目到 GitHub Pages，包括插件支持（如 jekyll-scholar）和 Bootstrap 样式管理。

---

## ✅ 1. 系统环境要求

### 📦 macOS / Linux 推荐环境

* Ruby（建议使用 chruby + ruby-install 安装 Ruby 3.4.4）
* Node.js（用于管理 Bootstrap 样式）
* Bundler（用于安装 Jekyll 依赖）

安装示例：

```bash
brew install ruby-install chruby node
ruby-install ruby 3.4.4
chruby ruby-3.4.4
gem install bundler
```

### 🪟 Windows 安装方法

1. 安装 [Ruby+Devkit](https://rubyinstaller.org/downloads/)（建议 Ruby 3.1 以上）
2. 安装 Node.js：[https://nodejs.org](https://nodejs.org)
3. 使用终端（推荐 Git Bash）执行：

```bash
gem install bundler
bundle install
```

⚠️ Windows 下建议使用 [MSYS2](https://www.msys2.org/) 环境以确保 gem 原生扩展编译通过。

---

## ✅ 2. 安装依赖

```bash
bundle install
```

---

## ✅ 3. 本地构建与预览

每次进行 bundle exec jekyll serve,前，确认ruby的版本是不是3.4.4（chruby ruby-3.4.4）

```bash
bundle exec jekyll serve
```

浏览器访问：[http://127.0.0.1:4000](http://127.0.0.1:4000)

构建静态文件：

```bash
bundle exec jekyll build
```

输出位于 `_site/` 目录

---

## ✅ 4. 项目结构说明

| 路径            | 说明                 |
| ------------- | ------------------ |
| `_config.yml` | 网站配置               |
| `_pages/`     | 所有网页的 Markdown 页面  |
| `_data/`      | `.yml` 数据文件（团队成员等） |
| `assets/`     | 样式、JS、BibTex 等资源   |
| `_includes/`  | HTML 模板片段          |
| `_layouts/`   | 页面模板结构             |
| `ref.bib`     | 文献 BibTeX 文件       |
| `citesty.csl` | 引用样式文件             |

---

## ✅ 5. 插件支持 jekyll-scholar

在 `_config.yml` 中配置：

```yaml
plugins: ["jekyll/scholar"]
scholar:
  bibliography: ref.bib
  style: citesty
```

---

## ✅ 6. Bootstrap 主题管理（可选）

```bash
sh switch_theme.sh darkly
sh update_bootstrap.sh
```

Windows 用户可手动下载 bootswatch 主题并替换 `_sass/bootstrap.scss`

---

## ✅ 7. GitHub Actions 自动部署

项目使用 jekyll-scholar 等插件，需通过 GitHub Actions 自动构建。

示例 `.github/workflows/jekyll.yml`：

```yaml
name: Build and Deploy

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - uses: ruby/setup-ruby@v1
        with:
          ruby-version: 3.4.4

      - run: gem install bundler && bundle install
      - run: bundle exec jekyll build

      - uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
          publish_branch: gh-pages
```

确保 Pages 设置中使用 `gh-pages` 分支。

---

## ✅ 8. 常见问题与建议

* 修改 `_config.yml` 后需重启 `jekyll serve`
* 页面 `.md` 必须有 `permalink:` 字段
* Windows 用户注意 gem 编译与路径兼容
* `_site/` 文件夹不应提交到 GitHub
* _data: 修改增加信息
* _pages： 改变页面布局
* assets下的ref.bib: publication的信息，在这里更新和添加
* images: 所有的图片信息，都在这里，增加删除也把路径放到这里，方便查找
* paper: publication里面的pdf那的超链接，可以上传PDF到这个文件里。但是建议直接在publication 的PDF放入链接跳转页面了。那样子方便点
* _config.yml: 配置基本信息，需要修改的在这里修改， 修改 `_config.yml` 后需重启 `jekyll serve`

---



