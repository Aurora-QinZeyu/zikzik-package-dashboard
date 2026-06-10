# New vs Old Package Dashboards

这个仓库用于通过 GitHub Pages 托管新老包体对比分析看板。

> 注意：当前仓库和 GitHub Pages 均为公开访问，请不要上传不适合公开传播的数据。

## 看板入口

| 看板 | 口径 | 线上链接 | 仓库文件 |
|---|---|---|---|
| Meta CPI 看板 | 消耗 / 安装次数 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/) | `index.html` |
| Meta CPA 看板 | 消耗 / 订阅次数 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/meta-cpa/) | `meta-cpa/index.html` |
| Google CPI 看板 | 消耗 / 安装次数 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/google-cpi/) | `google-cpi/index.html` |
| Google CPA 看板 | 消耗 / 订阅次数 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/google-cpa/) | `google-cpa/index.html` |

## 口径说明

- CPI = 消耗 / 安装次数
- CPA = 消耗 / 订阅次数
- 节省金额按日计算后求和：
  - CPI 节省 = 新包当日安装次数 × (老包当日 CPI - 新包当日 CPI)
  - CPA 节省 = 新包当日订阅次数 × (老包当日 CPA - 新包当日 CPA)
