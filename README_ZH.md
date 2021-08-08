# github-proxy
[En](/README.md) | 中

## 介绍
一个基于浏览器端 JS 实现的在线 Github 代理。<br>
某些国家和地区屏蔽了 Github.com 和它的子页面。使用本代理，您可以：<br>
- 为 Github.com 设立一个镜像站。
- 为您的 github pages 设立镜像。

不需要任何服务器。你所需要的，只是一个 `CloudFlare Workers` 帐号。这些都是免费的。<br>

## 步骤
1. 前往 [https://dash.cloudflare.com/sign-up/workers](https://dash.cloudflare.com/sign-up/workers) 并注册一个帐号。<br><br>
<img align="center" src="https://cdn.jsdelivr.net/gh/katorlys/github-proxy/screenshots/1.PNG"><br><br>
2. 创建一个 Worker。<br><br>
<img align="center" src="https://cdn.jsdelivr.net/gh/katorlys/github-proxy/screenshots/2.PNG"><br><br>
3. 将 [index.js](https://cdn.jsdelivr.net/gh/katorlys/github-proxy/index.js) 中的代码复制到左边的代码框中，点击 “保存并部署” 并确认。你可以在帐号设置中设置二级域名；在本页面左上角可以设置镜像站的子域名。我在这里设置的是 “github-mirror”。<br><br>
<img align="center" src="https://cdn.jsdelivr.net/gh/katorlys/github-proxy/screenshots/3.PNG"><br><br>
4. 点击右边框中的 “发送” 来检查您的 Worker 是否正常工作。<br><br>
<img align="center" src="https://cdn.jsdelivr.net/gh/katorlys/github-proxy/screenshots/4.PNG"><br><br>
5. 一切就绪。享受您的镜像站吧：`https://second-subdomain.subdomain.workers.dev`.<br><br>
<img align="center" src="https://cdn.jsdelivr.net/gh/katorlys/github-proxy/screenshots/5.PNG"><br>

## What's more
您同样可以为您的 github pages 设立镜像。只需将 步骤3
```
const ASSET_URL = 'https://github.com'
```
中的 `https://github.com` 改成您 github pages 的域名，例如 `https://katorly.github.io`。<br>
<br>
您也可以连接到您自己的域名来设立镜像站。<br>

## Notice
- 一个免费的 CloudFlare 帐号包含每天 <b>10万</b> 次请求。如果您的请求次数用完了，镜像站将不再工作。但事实上，一天10万次对个人来说足够了。如果有需要，您可以升级到付费计划。
- 本仓库中的 `index.js` 来自 [https://github.com/EtherDream/jsproxy](https://github.com/EtherDream/jsproxy)。