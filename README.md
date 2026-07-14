# Yangyi Zhang — Personal Website

基于 **Jekyll** 的学术个人主页，设计参考 [wenzhi-ding.com](https://wenzhi-ding.com/)，简洁现代、响应式。

## 网站结构

```
personal-website/
├── _config.yml            # Jekyll 主配置（站名、域名、导航、社交链接）
├── _data/                 # —— 内容数据（改这里即可更新网站）——
│   ├── profile.yml        #   个人简介、头像、CV、联系方式
│   ├── positions.yml      #   现任职位
│   ├── education.yml      #   教育背景
│   ├── papers.yml         #   论文（working / published / other 三类）
│   ├── teaching.yml       #   教学经历
│   └── projects.yml       #   项目展示
├── _layouts/              # 页面布局
│   ├── default.html       #   基础布局（header + main + footer）
│   └── page.html          #   子页面布局
├── _includes/             # 可复用组件
│   ├── header.html        #   顶部导航
│   ├── footer.html        #   页脚
│   ├── social-links.html  #   社交图标
│   ├── info-row.html      #   职位/教育信息行
│   └── paper-card.html    #   论文卡片
├── _sass/                 # SCSS 样式
│   ├── _variables.scss    #   颜色/字体/间距变量
│   ├── _base.scss         #   基础样式
│   ├── _layout.scss       #   布局样式
│   └── _components.scss   #   组件样式
├── assets/
│   ├── css/main.scss      # 样式入口
│   ├── img/               # 头像、logo 等图片
│   └── papers/            # 论文 PDF
├── index.html             # 首页（About + Position + Education + Research）
├── teaching.html          # 教学页面
├── projects.html          # 项目页面
├── 404.html               # 404 页面
├── CNAME                  # 自定义域名配置 → yangyi-zhang.com
├── Gemfile                # Ruby 依赖
└── .gitignore
```

## 如何编辑内容

**90% 的更新只需改 `_data/` 下的 YAML 文件，无需碰 HTML/CSS。**

| 想改什么 | 改哪个文件 |
|---------|-----------|
| 名字、简介、头像、邮箱、CV | `_data/profile.yml` |
| 现任职位 | `_data/positions.yml` |
| 教育背景 | `_data/education.yml` |
| 添加/删除论文 | `_data/papers.yml` |
| 教学经历 | `_data/teaching.yml` |
| 项目展示 | `_data/projects.yml` |
| 导航栏菜单 / 社交链接 | `_config.yml` |
| 主题颜色/字体 | `_sass/_variables.scss` |

---

## 本地预览

需要安装 **Ruby**（≥ 2.7）和 **Bundler**。

```bash
cd personal-website
bundle install          # 首次运行安装依赖
bundle exec jekyll serve
```

浏览器打开 `http://localhost:4000` 即可预览。

> **Windows 用户**：推荐使用 [RubyInstaller](https://rubyinstaller.org/) 安装 Ruby + DevKit。

---

## 部署到 GitHub Pages + 自定义域名

### 1. 创建 GitHub 仓库

```bash
cd personal-website
git init
git add .
git commit -m "Initial commit: personal website"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

> 仓库名可以任意，例如 `yangyi-zhang.github.io` 或 `personal-website`。

### 2. 开启 GitHub Pages

1. 进入仓库 **Settings → Pages**
2. **Source** 选择 `Deploy from a branch`
3. **Branch** 选 `main` / `(root)` → 点击 **Save**
4. 等待 1–2 分钟，GitHub 会自动构建并部署

### 3. 绑定自定义域名 `yangyi-zhang.com`

仓库根目录已包含 `CNAME` 文件（内容为 `yangyi-zhang.com`），无需额外操作。

还需在你的**域名注册商 DNS 管理面板**中配置：

**方案 A：使用 Apex 域名（推荐）**

添加 4 条 A 记录指向 GitHub Pages IP：

| 类型 | 主机 | 值 |
|------|------|----|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

**方案 B：使用 www 子域名**

| 类型 | 主机 | 值 |
|------|------|----|
| CNAME | `www` | `<你的用户名>.github.io` |

### 4. 验证

- DNS 生效需等待几分钟到数小时（可用 `nslookup yangyi-zhang.com` 检查）
- GitHub Pages Settings 中确认 **Custom domain** 显示 `yangyi-zhang.com` 且 DNS check 通过
- 勾选 **Enforce HTTPS** 获取免费 SSL 证书

---

## 更新 `_config.yml` 中的 TODO 项

打开 `_config.yml`，搜索 `TODO` 替换以下内容：

- `email` — 你的真实邮箱
- `social.google_scholar` — Google Scholar 主页链接
- `social.github` — GitHub 主页链接
- `social.linkedin`（可选）— LinkedIn 主页链接
- `social.orcid`（可选）— ORCID 链接
- `social.twitter`（可选）— Twitter/X 链接

---

## 技术栈

- [Jekyll](https://jekyllrb.com/) — 静态站点生成器
- SCSS — 样式
- GitHub Pages — 免费托管
- Google Fonts (Inter + Lora) — 字体
