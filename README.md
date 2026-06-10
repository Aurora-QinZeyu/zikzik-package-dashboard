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
| 四组新老包体分日趋势看板 | 同期老包池对比，初期连续成本优势 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/final-group-daily-trends/) | `final-group-daily-trends/index.html` |

## 口径说明

- CPI = 消耗 / 安装次数
- CPA = 消耗 / 订阅次数
- 四组新老包体分日趋势看板允许新包上线前 1-3 天冷启动扰动，但优势段必须至少连续 3 天；优势首次中断的日期记为优势消失日
- 节省金额按日计算后求和：
  - CPI 节省 = 新包当日安装次数 × (老包当日 CPI - 新包当日 CPI)
  - CPA 节省 = 新包当日订阅次数 × (老包当日 CPA - 新包当日 CPA)
