## 私人访问统计（Umami）

网站已配置 Umami Cloud 接入，对应后台网站 `personal`（`gdfwj.github.io`）；部署后开始统计。
`_config.yml` 中的 `analytics.umami.website_id` 为空时不会加载统计脚本。
GitHub Pages 只托管静态页面，统计数据保存在你的 Umami Cloud 账户中，不写入本仓库。
Umami 用访问请求的 IP 推断国家、地区和城市，不保存原始 IP；另外会统计浏览量、页面、来源和浏览器等基本信息。
城市是 IP 数据库的估计结果，可能缺失或不准确，VPN / 代理通常显示出口节点位置，不代表访客实际所在城市。
这是第三方托管的私人统计后台，服务商仍负责处理数据。

### 启用

1. 在 [Umami Cloud](https://cloud.umami.is/) 注册或登录，选择 Hobby 免费方案（额度和保留期以当时套餐页面为准）。
2. 进入 **Websites → Add website**，名称可填 `Zihao Wang`，Domain 填 `gdfwj.github.io`（不带 `https://` 和路径）。
3. 打开该网站的 **Edit → Tracking code**，复制脚本里的 `data-website-id`，填入 `_config.yml` 的 `analytics.umami.website_id`。
   `script_url` 应与后台给出的脚本地址一致；默认是 `https://cloud.umami.is/script.js`。
4. 保持 **Share URL** 关闭 / 无分享链接，不把网站加入共享团队，也不创建公开统计看板。统计默认私有，只用自己的账户登录查看。
5. 将修改提交并推送到 GitHub Pages 当前使用的发布分支，等待 Pages 部署成功。
6. 访问 `https://gdfwj.github.io/`，然后在 Umami 网站统计中查看实时访问和 **Location → City** 城市维度。

Website ID 是公开的采集标识，会出现在网页源码中；它不是后台登录凭据，也不能用来读取私人报表。
密码、API key、访问数据导出文件不要放入这个公开仓库。

### 验证和日常使用

- 查看线上页面源码，确认有一个带自己 Website ID 的 Umami 脚本；浏览器开发者工具 Network 中应能看到脚本及采集请求成功。
- 网站仅在 `JEKYLL_ENV=production` 构建且 ID 非空时加入脚本；GitHub Pages 使用 production，本地默认开发构建不加载统计。
  `data-domains` 还将采集限制在 `gdfwj.github.io`。将来更换域名时同步修改这个值和 Umami 后台网站设置。
- 不因浏览器 Do Not Track 信号跳过统计（`data-do-not-track="false"`）。不采集当前页面 URL 的查询参数和 `#` 片段；未启用会话录屏或精确定位。
- 广告拦截、浏览器跟踪防护、禁用 JavaScript 或网络不可达会导致漏计；这里只统计启用后的页面访问，无法补查历史，也不统计直接打开 PDF 的访问。
- 排除自己：在访问主页时打开浏览器控制台，执行 `localStorage.setItem('umami.disabled', '1')`，然后刷新。
  恢复统计执行 `localStorage.removeItem('umami.disabled')`。此设置只针对当前浏览器、当前站点。
- 停止统计：将 `analytics.provider` 改为 `false`，或清空 `website_id`，再部署。既有数据仍由 Umami 后台管理。

官方说明：[地理位置与 IP](https://docs.umami.is/docs/metric-definitions)、[默认私有和分享链接](https://docs.umami.is/docs/enable-share-url)、[脚本配置](https://docs.umami.is/docs/tracker-configuration)、[免费方案](https://docs.umami.is/docs/cloud/faq)。

---

A Github Pages template for academic websites. This was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License. See LICENSE.md.

I think I've got things running smoothly and fixed some major bugs, but feel free to file issues or make pull requests if you want to improve the generic template / theme.

### Note: if you are using this repo and now get a notification about a security vulnerability, delete the Gemfile.lock file. 

# Instructions

1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section
1. (Optional) Use the Jupyter notebooks or python scripts in the `markdown_generator` folder to generate markdown files for publications and talks from a TSV file.

See more info at https://academicpages.github.io/

## To run locally (not on GitHub Pages, to serve on your own computer)

1. Clone the repository and made updates as detailed above
1. Make sure you have ruby-dev, bundler, and nodejs installed: `sudo apt install ruby-dev ruby-bundler nodejs`
1. Run `bundle clean` to clean up the directory (no need to run `--force`)
1. Run `bundle install` to install ruby dependencies. If you get errors, delete Gemfile.lock and try again.
1. Run `bundle exec jekyll liveserve` to generate the HTML and serve it from `localhost:4000` the local server will automatically rebuild and refresh the pages on change.

# Changelog -- bugfixes and enhancements

There is one logistical issue with a ready-to-fork template theme like academic pages that makes it a little tricky to get bug fixes and updates to the core theme. If you fork this repository, customize it, then pull again, you'll probably get merge conflicts. If you want to save your various .yml configuration files and markdown files, you can delete the repository and fork it again. Or you can manually patch. 

To support this, all changes to the underlying code appear as a closed issue with the tag 'code change' -- get the list [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aclosed%20is%3Aissue%20label%3A%22code%20change%22%20). Each issue thread includes a comment linking to the single commit or a diff across multiple commits, so those with forked repositories can easily identify what they need to patch.
