# 受控 HTTPS 发布方案

这个目录是纯静态看板，可以发布到支持访问控制的静态托管服务，再把受控链接放进飞书文档或知识库。

## 推荐：Cloudflare Pages + Access

### 1. 准备仓库

当前静态站点目录：

```text
github-pages-site/
```

入口页面：

| 看板 | 路径 |
|---|---|
| Meta CPI | `/` |
| Meta CPA | `/meta-cpa/` |
| Google CPI | `/google-cpi/` |
| Google CPA | `/google-cpa/` |

### 2. 在 Cloudflare Pages 创建项目

1. 打开 Cloudflare Dashboard。
2. 进入 `Workers & Pages`。
3. 选择 `Create application` -> `Pages` -> `Connect to Git`。
4. 选择这个仓库。
5. 构建配置填写：

```text
Build command: 留空
Build output directory: /
Root directory: 留空
```

如果 Cloudflare 连接的是上层仓库，而不是 `github-pages-site` 这个独立仓库，则需要把：

```text
Root directory: github-pages-site
Build output directory: /
```

### 3. 打开 Cloudflare Access 访问控制

1. 进入 `Zero Trust`。
2. 进入 `Access` -> `Applications`。
3. 新建 `Self-hosted` 应用。
4. Domain 填 Pages 生成的域名，例如：

```text
package-dashboard.pages.dev
```

5. Policy 建议选择：

```text
Allow
Emails ending in: 你的公司邮箱域名
```

或指定具体成员邮箱。

完成后，访问看板时会先经过 Cloudflare 登录校验。

### 4. 放到飞书

在飞书文档或知识库里放受控链接：

```text
https://你的域名/google-cpa/
```

如果飞书当前版本支持嵌入网页，可以选择嵌入；如果嵌入时遇到登录页或跨域限制，就改成按钮/链接跳转。跳转方式最稳定。

## 备用：Vercel / Netlify

也可以发布到 Vercel 或 Netlify，但需要开启团队/项目级访问保护，或在前面加 Cloudflare Access。

注意：只把 GitHub 仓库改成 private 不等于看板链接受保护。真正的访问控制必须发生在托管服务入口。

## 已添加的基础防护

本目录已经包含：

| 文件 | 作用 |
|---|---|
| `_headers` | 给 Cloudflare Pages / Netlify 添加 `noindex` 和安全响应头 |
| `robots.txt` | 阻止搜索引擎抓取 |

这些只能降低被发现和收录的风险，不能替代登录鉴权。

