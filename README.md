# New vs Old Package Dashboards

这个仓库用于托管新老包体对比分析看板。看板是纯静态 HTML，可以部署为受控 HTTPS 网页，再把链接放进飞书文档或知识库。

> 注意：不要把包含业务数据的看板继续用公开 GitHub Pages 裸链分享。私密查看请使用 [受控 HTTPS 发布方案](DEPLOY_PRIVATE.md)。

## 看板入口

| 看板 | 口径 | 受控 HTTPS 路径 | 仓库文件 |
|---|---|---|---|
| Meta CPI 看板 | 消耗 / 安装次数 | `/` | `index.html` |
| Meta CPA 看板 | 消耗 / 订阅次数 | `/meta-cpa/` | `meta-cpa/index.html` |
| Google CPI 看板 | 消耗 / 安装次数 | `/google-cpi/` | `google-cpi/index.html` |
| Google CPA 看板 | 消耗 / 订阅次数 | `/google-cpa/` | `google-cpa/index.html` |

## 口径说明

- CPI = 消耗 / 安装次数
- CPA = 消耗 / 订阅次数
- 节省金额按日计算后求和：
  - CPI 节省 = 新包当日安装次数 × (老包当日 CPI - 新包当日 CPI)
  - CPA 节省 = 新包当日订阅次数 × (老包当日 CPA - 新包当日 CPA)
