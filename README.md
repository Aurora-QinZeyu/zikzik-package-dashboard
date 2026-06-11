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
| 四组素材归因看板 | 逐日对齐老包池 CPA，拆解素材解释金额 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/final-group-daily-trends/material-attribution.html) | `final-group-daily-trends/material-attribution.html` |

## 素材归因看板

素材归因看板用于回答：新包相对老包池的 CPA 差异，具体由哪些素材主题贡献，能解释多少金额。

| 组 | 对比口径 | 归因窗口 | 线上链接 | 数据文件 |
|---|---|---|---|---|
| Zikzik | Zikzik vs CoupleLens / Dradra / Usgen | 2026-05-20 至 2026-06-07，CPA 初期优势期 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/final-group-daily-trends/zikzik-material-attribution.html) | `final-group-daily-trends/zikzik_daily_aligned_material_attribution.csv` |
| Beyo | Beyo vs Minimix / Vimi / Viyo / CoupleLens | 2026-03-07 至 2026-03-26，CPA 初期优势期 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/final-group-daily-trends/beyo-material-attribution.html) | `final-group-daily-trends/beyo_daily_aligned_material_attribution.csv` |
| Heyo | Heyo vs Minimix / Vimi / Viyo / CoupleLens | 2026-03-13 至 2026-03-19，CPA 初期优势期 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/final-group-daily-trends/heyo-material-attribution.html) | `final-group-daily-trends/heyo_daily_aligned_material_attribution.csv` |
| Beatmo | Beatmo vs Minimix / Vimi / Viyo / CoupleLens | 2026-03-31 至 2026-04-17，完整观察期；无 CPA 初期连续优势 | [打开看板](https://aurora-qinzeyu.github.io/zikzik-package-dashboard/final-group-daily-trends/beatmo-material-attribution.html) | `final-group-daily-trends/beatmo_daily_aligned_material_attribution.csv` |

当前归因结果摘要：

| 组 | CPA 净结果 | Top 6 正贡献素材 | 解释结论 |
|---|---:|---:|---|
| Zikzik | $9,461 | $8,190 | 头部素材可以解释大部分优势 |
| Beyo | $17,236 | $16,206 | 头部素材解释度最高 |
| Heyo | $3,258 | $3,357 | 基本由少数素材拉动 |
| Beatmo | -$585 | $316 | 反例；正贡献不足以抵消负贡献 |

## 口径说明

- CPI = 消耗 / 安装次数
- CPA = 消耗 / 订阅次数
- 四组新老包体分日趋势看板允许新包上线前 1-3 天冷启动扰动，但优势段必须至少连续 3 天；优势首次中断的日期记为优势消失日
- 节省金额按日计算后求和：
  - CPI 节省 = 新包当日安装次数 × (老包当日 CPI - 新包当日 CPI)
  - CPA 节省 = 新包当日订阅次数 × (老包当日 CPA - 新包当日 CPA)
- 素材归因金额按素材逐日计算后求和：
  - 素材 CPA 贡献 = 新包该素材当日订阅次数 × 当日老包池 CPA - 新包该素材当日消耗
  - 正贡献表示该素材以低于当日老包池 CPA 的成本贡献订阅
  - 负贡献表示该素材高于当日老包池 CPA，会抵消头部素材带来的优势
- 气泡图含义：
  - 横轴 = 素材消耗规模
  - 纵轴 = CPA，越低越好
  - 圆圈大小 = 订阅数
  - 红色虚线 = 同窗口老包池平均 CPA
  - 上半块展示新包素材，下半块展示老包池素材，避免新老素材重叠造成误读

## 文件结构

```text
final-group-daily-trends/
  index.html                                  # 四组分日趋势主看板
  final_group_daily_trends.csv                # 分日趋势数据
  material-attribution.html                   # 四组素材归因总览
  zikzik-material-attribution.html            # Zikzik 素材归因页
  beyo-material-attribution.html              # Beyo 素材归因页
  heyo-material-attribution.html              # Heyo 素材归因页
  beatmo-material-attribution.html            # Beatmo 素材归因页
  *_daily_aligned_material_attribution.csv    # 各组素材逐日对齐归因数据
```

## 更新流程

上层分析项目中保留了生成脚本：

```text
scripts/build_final_group_daily_trends.py
scripts/build_group_material_attribution_dashboards.py
```

更新数据后，先在上层分析项目重新生成静态文件，再进入本仓库提交并推送：

```bash
python3 scripts/build_final_group_daily_trends.py
python3 scripts/build_group_material_attribution_dashboards.py
git -C github-pages-site status --short
git -C github-pages-site add README.md final-group-daily-trends/
git -C github-pages-site commit -m "Update package dashboards"
git -C github-pages-site push origin main
```

GitHub Pages 发布后，线上链接通常会在数十秒到数分钟内刷新。
