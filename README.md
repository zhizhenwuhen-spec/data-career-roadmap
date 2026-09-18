# data-career-roadmap ｜ 数据分析 / 大数据 求职学习路线

> **目标岗位**：网易 · AI 数据分析师（主攻） ／ 神州信息 · 大数据开发（保底）
> **起跑日期**：2026-09-18 ｜ **打卡规则**：每完成一项即 commit 一次，目标「连续绿色格子」
> **配套文档**：[`docs/plan/01-GitHub学习复现项目清单.md`](docs/plan/01-GitHub学习复现项目清单.md)（开源项目核验清单；所有星标与最后推送时间均为联网实测值，非印象值）

---

## 一、四站路线图

| 站点 | 时间 | 学什么 | 主线资源 | 验收标准 |
| --- | --- | --- | --- | --- |
| **第 1 站 SQL**（P0 第一缺口） | 2026-09-17 ~ 11-30 | 窗口函数、**条件聚合（CASE + SUM）**、多表 JOIN、CTE、集合运算 | `civilian7/sql-tutorial`（自带 75 万行数据 + 1065 题带答案）<br>起步：`sqlmother.yupi.icu`（网页闯关，零安装） | 限时 10 分钟手撕 1 题 + 口述 3 题 |
| **第 2 站 统计 / AB / 指标体系** | 2026-11-16 ~ 2027-01-10 | 置信区间、假设检验、贝叶斯、AB 全流程、留存 / 漏斗 / 北极星指标 | `Ali12hamdan/ab-test-cookie-cats`（与项目 2 **同数据集**，可对答案） | 能独立产出「实验结论 + 是否上线」决策 |
| **第 3 站 数仓 + 大数据生态**（概念级） | 2027-01-11 ~ 01-31 | 数仓分层、Hive vs Spark SQL、数据质量与一致性 | 读：`heibaiying/BigData-Notes`<br>跑：`DataWithBaraa/sql-data-warehouse-project` | 能画分层架构图并讲清每层职责 |
| **第 4 站 ML + 游戏数据 + 大模型** | 2027-02 | ML 原理、特征筛选、评价指标、游戏指标拆解、AI 辅助分析并审核 AI 产出 | `LongxingTan/Machine-learning-interview` + `microsoft/data-formulator` | 概念卡 ≥20 张；能用自然语言生成分析并**逐行核对生成的代码** |

## 二、三个简历项目

| 项目 | 时间 | 一句话定位 | 关键产出 |
| --- | --- | --- | --- |
| **项目 1 · 光伏购电优化** | 2027-01-11 ~ 02-28 | 数据分析叙事 + 负荷预测 + 线性规划决策 + 数仓分层 | 优化方案 + 预测模型 + 分层数仓 + 看板 |
| **项目 2 · 移动游戏 AB 实验与留存分析** | MVP 2027-02-08 ~ 02-28 | 开源资源最薄弱的一环，**是补空白不是复现** → 简历价值最高 | 实验设计 → SRM 体检 → 统计检验 → 上线决策 → 留存/漏斗看板 |
| **项目 3 · 日志 ETL 管道** | 2027-05-01 ~ 06-30 | ODS→DWD→DWS→ADS 四层，Spark SQL + MySQL + cron | `run_pipeline.sh` 一条命令跑完 + 数据质量报告 |
| **BI 看板**（三项目通用） | 全阶段 | 走 ECharts / pyecharts 代码路线（**不碰 Power BI**：样本全是 .pbix 二进制，无法 diff） | 可双击打开的交互式 HTML 看板（≥3 图） |

## 三、阶段 → 开源项目映射总表

> **主线** = 必须跑完 ｜ **补充** = 需要时再打开 ｜ **参考** = 只读代码/架构，不试图跑通

| 计划阶段 | 主线仓库 | 补充仓库 | 参考 / 避坑 |
| --- | --- | --- | --- |
| **第 1 站 SQL** | `civilian7/sql-tutorial` ⭐226 | `datawhalechina/wonderful-sql` ⭐1091<br>`datacharmer/test_db` ⭐4440<br>`sqlmother.yupi.icu`（网页，⭐4388） | `devrimgunduz/pagila` ⭐1119（Postgres 专项）<br>避坑：`DataWithDanny/sql-masterclass`（停更 3.5 年） |
| **第 2 站 统计 / AB / 指标体系** | `Ali12hamdan/ab-test-cookie-cats` ⭐1（与项目 2 同数据集）<br>`AllenDowney/ThinkBayes2` ⭐2080 | `Ucazin/ab-testing-framework` ⭐0<br>`baumanab/udacity_ABTesting` ⭐84 | `retentioneering-tools` ⭐919<br>`lifelines` ⭐2611<br>`david26694/cluster-experiments` ⭐56 |
| **第 3 站 数仓 + 大数据生态** | `heibaiying/BigData-Notes` ⭐16.9k（纯文档速查） | `DataWithBaraa/sql-data-warehouse-project` ⭐952（唯一确定能跑完）<br>`MrSuiChuan/data-warehouse-learning` ⭐1243（**只读架构，别硬跑**） | `big-data-europe/docker-hive` ⭐1081<br>`lhq-123/Spark-Flink-DataWarehouse` ⭐46（只读 ADS SQL） |
| **第 4 站 ML + 游戏数据 + 大模型** | `LongxingTan/Machine-learning-interview` ⭐336 | `datawhalechina/hands-on-data-analysis` ⭐1531<br>`AllenDowney/ThinkStats2` ⭐4231 | `microsoft/data-formulator` ⭐17254（JD 直接命中） |
| **项目 1 光伏购电** | `samirsaci/supply-planning` ⭐16（PuLP 范本） | `shengwei-peng/PV-Power-Generation-Forecasting` ⭐23 | `pyecharts` ⭐15.8k<br>UCI 家庭用电数据集（静态 zip 可直下，免登录） |
| **项目 2 游戏 AB 与留存** | **自行构建**（Cookie Cats 数据集已核验可用） | 对答案用 `Ali12hamdan/ab-test-cookie-cats` ⭐1 | `dbt-labs/jaffle_shop_duckdb` ⭐289<br>`microsoft/data-formulator` ⭐17254 |
| **项目 3 日志 ETL 管道** | `databricks/LearningSparkV2` ⭐1405（chapter7 自带 22MB 真实访问日志）<br>`josephmachado/efficient_data_processing_spark` ⭐393 | `josephmachado/beginner_de_project` ⭐594<br>`big-data-europe/docker-hive` ⭐1081 | `abeltavares/batch-data-pipeline` ⭐90（**只抄 20 条质量检查**）<br>`Smars-Bin-Hu/EComDWH...` ⭐173（抄分层规范） |
| **全阶段 BI 产出物** | `pyecharts/pyecharts` ⭐15.8k（MIT） | `pyecharts-gallery` ⭐1.4k（MIT，抄配方）<br>`evidence-dev/evidence` ⭐6947 | `dataease/dataease` ⭐24444<br>避坑：`iGaoWei/BigDataView`（无许可证） |

## 四、14 天起步清单（2026-09-18 ~ 09-30）

进度逐日记录在 [`log/2026-09.md`](log/2026-09.md)。

| 时间 | 动作 | 产出 | 状态 |
| --- | --- | --- | --- |
| **09-18（已完成）** | 环境确认（git 2.55 / Python 3.12 / Node 24） | 环境确认 | ✅ |
| **09-18（已完成）** | 建本仓库 + README + 打卡文件，完成首次 commit | 仓库链接 | ✅ |
| **09-18（已完成）** | clone `datawhalechina/wonderful-sql`（中文概念铺底） | 本地中文教程 | ✅ |
| **09-18 今晚** | `sqlmother.yupi.icu` 闯前 5 关（零安装、即时反馈） | 手感 + 截图 | ⬜ |
| 09-19 | 装 MySQL 8.0 + 客户端（Navicat Premium Lite 已免费，或 DBeaver）；跑通 `SELECT 1` | 本地 MySQL 可用 | ⬜ |
| 09-19 | 装 Docker Desktop（后面 `sql-tutorial`、`pagila`、`docker-hive` 都要用） | Docker 可用 | ⬜ |
| 09-19 | `wonderful-sql` ch00 环境搭建 + ch01 初识数据库 | 打卡 commit | ⬜ |
| 09-20 | ch02 基础查询与排序；执行 `materials/create_table_sql/shop.sql` 与 `world.sql` | 两个练习库建好 | ⬜ |
| 09-20 | SQL 母网闯到 20 关 | 截图入打卡 | ⬜ |
| 09-21 | 光伏项目 STAR 简历段 v0.1（数字现成：2000 万 → 1400 万，-30%） | `resume/project-v0.1.md` | ⬜ |
| 09-20 ~ 09-23 | ch03（视图/子查询/函数/谓词/**CASE**，条件聚合的地基，务必手敲） | ch03 习题完成 | ⬜ |
| 09-20 ~ 09-23 | ch04（集合运算 + JOIN） | ch04 习题完成 | ⬜ |
| 09-20 ~ 09-23 | clone `civilian7/sql-tutorial`，Docker 起 MySQL 容器，生成 `--size small`（75 万行） | 30 表数据库可用 | ⬜ |
| 09-20 ~ 09-23 | 读 `sql-tutorial` 表结构，自出「订单 + 订单明细 + 商品」三表 JOIN 自测题 5 道并作答 | 5 道自测题 | ⬜ |
| 第 2 周 | `sql-tutorial` beginner 00–07；ch05 SQL 高级处理（窗口函数 / GROUPING / 存储过程） | 题集 + 习题 | ⬜ |
| 第 2 周 | 牛客 SQL 累计 ≥20 题；跑通 `python -m src.verify.verify` | 正确率记录 | ⬜ |
| 第 2 周 | 建「AI 辅助写 SQL」留档（每次记录：**我让 AI 做了什么 + 我校验了什么**），目标 ≥3 条 | [`docs/ai-assisted-sql.md`](docs/ai-assisted-sql.md) | ⬜ |

### 14 天里程碑自查（09-30）

- [ ] 本仓库 ≥10 次 commit、14 天中 ≥12 天有绿色格子
- [ ] 本地 MySQL 有 2 个可用练习库（shop/world + `sql-tutorial` 的 30 表 75 万行）
- [ ] `wonderful-sql` ch00–ch05 完成，ch06 至少手写 3 题
- [ ] 牛客 SQL ≥20 题、SQL 母网 ≥20 关
- [ ] 能不看文档手写「GROUP BY + CASE WHEN 条件聚合」与「ROW_NUMBER() 分组取 Top1」
- [ ] 「AI 辅助写 SQL」留档 ≥3 条
- [ ] **娱乐回血时间一天都没被砍**（硬红线）

## 五、目录结构

```
data-career-roadmap/
├── README.md                    # 本文件：路线图 + 映射总表 + 14 天清单
├── log/                         # 每日打卡（一个月一个文件）
│   └── 2026-09.md
├── docs/
│   ├── ai-assisted-sql.md       # 「AI 辅助 + 人工校验」留档（JD 第 2-3 条直接命中）
│   └── plan/                    # 参考文档（开源项目核验清单）
├── sql/                         # 自己手写的练习 SQL（按天/按题命名）
└── resume/                      # 简历段落与项目 STAR 描述
```

> 第三方教材仓库统一 clone 到 **本仓库之外** 的 `../vendor-repos/`（见 `.gitignore` 说明），**不提交进本仓库**。

## 六、引用红线（务必遵守）

1. **无许可证仓库只能学、不能搬**：`wonderful-sql`、`heibaiying/BigData-Notes`、`juicy-bigdata`、`lhq-123/Spark-Flink-DataWarehouse`、`iGaoWei/BigDataView`、`yyhsong/iDataV`、`datawhalechina/hands-on-data-analysis` **均无许可证声明** → 教材内容、题目、代码**不得复制进本仓库**；本仓库只放**自己手写的 SQL、笔记、结论**。
2. **可安全复用（宽松许可）**：`pyecharts`（MIT）、`pyecharts-gallery`（MIT）、`vueDataV`（MIT）、`evidence`（MIT）、`ali12hamdan/ab-test-cookie-cats`、`civilian7/sql-tutorial`（代码 MIT，**内容 CC BY-NC-SA 非商用**）、`MrSuiChuan/data-warehouse-learning`（Artistic-2.0）、`Smars-Bin-Hu/EComDWH...`（MIT）、`abeltavares/batch-data-pipeline`（MIT）。
3. **fork 陷阱**：`data-warehouse-learning` 有多个 0 star 同名 fork，认准 ⭐1243 的 `MrSuiChuan/data-warehouse-learning`。
4. **课程引流型仓库**（代码可用，README 下半是卖课闭环）：`DataWithBaraa/sql-data-warehouse-project`、`josephmachado/efficient_data_processing_spark`、`DataTalksClub/data-engineering-zoomcamp` —— 当纯代码仓库用，别被引流带走。
