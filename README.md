# 私域运营笔记 · 静态推广站

GitHub Pages 静态站，6 篇行业向软文 + 自然引流到 wechatx.top。

## 文件结构

```
wx-blog/
├── index.html                          首页（文章索引）
├── assets/style.css                    样式
├── posts/
│   ├── scrm-vs-excel.html
│   ├── wechat-friend-organize.html
│   ├── private-traffic-2026.html
│   ├── group-member-analysis.html
│   ├── enterprise-vs-personal.html
│   ├── data-compliance.html
│   └── about.html
├── sitemap.xml                         (上线前替换 USERNAME)
└── robots.txt                          (上线前替换 USERNAME)
```

## 部署到 GitHub Pages —— 三步上线

### 1. 在 GitHub 创建仓库

去 https://github.com/new 创建一个仓库，名字必须是 `<你的GitHub用户名>.github.io`（这种名字仓库会自动作为个人主页发布）。

例：你的用户名是 `tomzhang`，仓库就叫 `tomzhang.github.io`。

### 2. 替换 sitemap / robots 中的占位符

把 `sitemap.xml` 和 `robots.txt` 里的 `USERNAME` 全部替换为你的 GitHub 用户名。

```powershell
$user = "你的用户名"
(Get-Content D:\wx-blog\sitemap.xml) -replace 'USERNAME', $user | Set-Content D:\wx-blog\sitemap.xml
(Get-Content D:\wx-blog\robots.txt)  -replace 'USERNAME', $user | Set-Content D:\wx-blog\robots.txt
```

### 3. 推送到 GitHub

```powershell
cd D:\wx-blog
git init
git branch -M main
git add .
git commit -m "init"
git remote add origin https://github.com/<你的用户名>/<你的用户名>.github.io.git
git push -u origin main
```

推送后等 1-2 分钟，访问 `https://<你的用户名>.github.io/` 即可看到。

## 上线后必做的 SEO 动作

1. **Google Search Console** 添加站点 → 提交 sitemap.xml
2. **Bing Webmaster Tools** 同上
3. **百度站长平台** 同上
4. 给 wechatx.top 加一个 footer 链接指向这个内容站，形成双向 backlink

## 后续运营建议

- **频率**：每周 1-2 篇新文章，保持站点新鲜度（搜索引擎喜欢更新频繁的站）
- **关键词**：标题/H2/正文均出现"微信好友"、"私域运营"、"SCRM"等长尾词
- **外链建设**：在知乎、小红书、即刻等平台写同主题简短版本，文末附本站链接
- **内链结构**：每篇文章末尾引用 1-2 篇同站其他文章

## 内容合规说明

所有文章基于"用户自有数据 + 合规整理"为前提撰写，避免任何越界场景描述。这种方向反而更利于：

- ✅ 长期被 Google / 百度收录（违规内容会被 K 站）
- ✅ 在知乎 / 小红书发布不被判违规
- ✅ B 端客户更愿意采购（合规背书）
