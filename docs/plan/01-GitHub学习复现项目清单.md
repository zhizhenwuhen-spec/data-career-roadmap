# GitHub 学习复现项目清单（对照《入职计划 v2》四站 + 三项目）

- 编制：尚书省 · 检索官（任务：为 v2 入职计划配套「可学习复现的 GitHub 开源项目」）
- 编制时间：2026-09-17
- 依据：`入职计划_v2.md`（四站 + 两支线 + 三项目）、`网易岗位深度报告.md`（W-006）、`岗位深度报告.md`（W-002）
- **核验口径**：所有星标数与最后推送时间均为本次联网实测（GitHub REST API、ungh.cc 实时代理、shields.io 徽章三源交叉），非印象值；「能不能跑」的判断基于实测文件树/源码，不采信 README 自述；未能核验者一律标注
- **使用原则**：每个阶段只开「1 个主线 + 1 个补充」；主线必须能本地跑起来

---

## 〇、结论先行

**先给您一句最重要的话：GitHub 能给您的比想象中多，但方向和直觉相反——SQL 与 ETL 有极好的开源资源，而 A/B 实验方向恰恰是「高星仓库没用、低星仓库才是宝」。**

1. **第 1 站 SQL 有全场最好的资源**：`civilian7/sql-tutorial`（⭐226，自带 75 万行数据 + 27 课 + **1065 题带答案** + 五方言 + Docker）能独立撑起整站；配合 **`sqlmother.yupi.icu`（⭐4388 的开源 SQL 闯关教程，纯网页免安装）** 起步、`datawhalechina/wonderful-sql`（⭐1091，中文、唯一活跃到 2026-08）铺概念。
2. **第 2 站 A/B 实验是个「反常区」**：高星仓库（如 ⭐26k 的 pumpkin-book）多是纯公式推导无代码；真正有「真实数据 + 完整统计链路 + 结论」的 `Ali12hamdan/ab-test-cookie-cats` **只有 1 星**。**而且它用的就是您项目 2 要用的 Cookie Cats 数据集（90,189 玩家已随仓库提交，免 Kaggle 账号）** —— 这是本次检索最大的意外收获：您等于拿到了一个可直接对答案的「标准答案卡尺」。
3. **第 3 站数仓要严格区分「能跑」和「该读」**：`MrSuiChuan/data-warehouse-learning`（⭐1243）**是文档+截图型仓库**（根目录只有 `pom.xml` + `src/main`，34MB 几乎全是图片），需 15 个组件集群——**只读架构，别硬跑**。真正在您笔记本上能跑完的分层数仓是 `DataWithBaraa/sql-data-warehouse-project`（⭐952，Bronze/Silver/Gold + 星型模型 + 真实 CSV，全程最低门槛）。
4. **项目 3 的日志 ETL 有现成骨架可抄**：`databricks/LearningSparkV2`（⭐1405，Databricks 官方）的 **chapter7 自带 22MB 真实 Web 访问日志**，格式与 NASA 日志同构——这是「日志解析 + Spark SQL」最省力的起点。
5. **BI 看板别碰 Power BI 的死胡同**：微软官方 `powerbi-desktop-samples` 里**几乎全是 .pbix 二进制**，GitHub 上无法 diff、面试官也看不到您的建模逻辑。改用 `pyecharts`（⭐15.8k，MIT）半天出交互式 HTML 看板，或 `evidence`（⭐6947）/ `dataease`（⭐24444，国产对标 FineBI）。
6. **有一处 JD 直接命中被原计划漏了**：网易 JD 第 2-3 条点名「大模型辅助分析 + 审核 AI 产出」，`microsoft/data-formulator`（⭐17254）正是这个——**用自然语言生成数据分析与图表，且生成的 pandas 代码可读可核对**，天然是「我会审 AI 产出」的实操素材。
7. **必须并行刷题站**：GitHub 补的是「知识 + 项目」，补不了「面试限时手写 SQL」的速度与手感——牛客 / 力扣不可省。而「AB 样本不平衡怎么办」「贝叶斯手算」「指标该选哪个」这三类**判断题**，任何仓库都给不了答案，只能靠 Kohavi 的书 + ThinkBayes2 + 指标体系方法论。

---

## 一、映射总表：计划阶段 → GitHub 项目

> **主线** = 必须跑完 ｜ **补充** = 需要时再打开 ｜ **参考** = 只读代码/架构，不试图跑通

| 计划阶段 | 岗位需求 | 主线仓库 | 补充仓库 | 参考 / 避坑 |
| --- | --- | --- | --- | --- |
| **第 1 站 SQL**<br>2026-09-17 ~ 11-30 | 网易：熟练 SQL（窗口/条件聚合）、面试口述 + 笔试手写<br>神州：熟悉至少一种数据库语言 | `civilian7/sql-tutorial` ⭐226 | `datawhalechina/wonderful-sql` ⭐1091<br>`datacharmer/test_db` ⭐4440<br>**`sqlmother.yupi.icu`**（网页，⭐4388） | `devrimgunduz/pagila` ⭐1119（Postgres 专项）<br>避坑：`DataWithDanny/sql-masterclass`（停更 3.5 年） |
| **第 2 站 统计 / AB / 指标体系**<br>2026-11-16 ~ 2027-01-10 | 网易必修核心：置信区间、假设检验、贝叶斯、AB 全流程、留存/漏斗/北极星 | **`Ali12hamdan/ab-test-cookie-cats`** ⭐1（与项目 2 同数据集）<br>`AllenDowney/ThinkBayes2` ⭐2080 | `Ucazin/ab-testing-framework` ⭐0（流程模板）<br>`baumanab/udacity_ABTesting` ⭐84（设计文档范本）<br>`dipanjanchoudhury/mobile-game-retention-analysis` ⭐5 | `retentioneering/retentioneering-tools` ⭐919（回流路径）<br>`lifelines` ⭐2611（留存曲线/Cox）<br>`david26694/cluster-experiments` ⭐56（样本量） |
| **第 3 站 数仓 + 大数据生态（概念级）**<br>2027-01-11 ~ 01-31 | 神州面经必问：数仓分层、Hive vs Spark SQL、数据质量一致性 | `heibaiying/BigData-Notes` ⭐16.9k（中文速查手册，**纯文档**） | **`DataWithBaraa/sql-data-warehouse-project`** ⭐952（唯一确定能跑完的分层数仓）<br>`MrSuiChuan/data-warehouse-learning` ⭐1243（读架构） | `Smars-Bin-Hu/EComDWH...` ⭐173（抄分层规范）<br>`big-data-europe/docker-hive` ⭐1081（摸真 Hive）<br>`lhq-123/Spark-Flink-DataWarehouse` ⭐46（只读 ADS SQL） |
| **第 4 站 ML + 游戏数据 + 大模型**<br>2027-02 | 网易面试：ML 原理、特征筛选、评价指标、游戏指标拆解；JD 第 2-3 条：大模型辅助分析 + 审 AI 产出 | `LongxingTan/Machine-learning-interview` ⭐336 | `datawhalechina/hands-on-data-analysis` ⭐1531<br>`AllenDowney/ThinkStats2` ⭐4231 | **`microsoft/data-formulator`** ⭐17254（JD 直接命中）<br>`retentioneering-tools` ⭐919（游戏行为路径） |
| **项目 1 光伏购电改造**<br>2027-01-11 ~ 02-28 | 数据分析叙事 + 预测 + 线性规划 + 数仓分层 + BI | `samirsaci/supply-planning` ⭐16（PuLP 线性规划范本） | `shengwei-peng/PV-Power-Generation-Forecasting` ⭐23 | `pyecharts` ⭐15.8k（看板产出）<br>`Kaggle Solar Power Generation`（已核验可下载） |
| **项目 2 游戏 AB 与留存**<br>MVP 2027-02-08 ~ 02-28 | 网易 JD 第 4 条 + 笔试留存归因 + 二面 AB 原题 | **自行构建**（Cookie Cats 已核验可用）<br>对答案用 `Ali12hamdan/ab-test-cookie-cats` ⭐1 | `dipanjanchoudhury/mobile-game-retention-analysis` ⭐5<br>`retentioneering-tools` ⭐919 | `dbt-labs/jaffle_shop_duckdb` ⭐289（指标体系落到 SQL）<br>`microsoft/data-formulator` ⭐17254（AI 辅助出图） |
| **项目 3 日志 ETL 管道**<br>2027-05-01 ~ 06-30 | 神州：ETL 设计/开发、Linux/Shell、Spark SQL 四层、数据质量、监控 | **`databricks/LearningSparkV2`** ⭐1405（chapter7 自带 22MB 真实访问日志）<br>`josephmachado/efficient_data_processing_spark` ⭐393 | `josephmachado/beginner_de_project` ⭐594（`make up` 一条命令）<br>`big-data-europe/docker-hive` ⭐1081 | `abeltavares/batch-data-pipeline` ⭐90（**只抄 20 条质量检查**）<br>`Smars-Bin-Hu/EComDWH...` ⭐173（抄规范）<br>`DataTalksClub/data-engineering-zoomcamp` ⭐45607（只取 2 样） |
| **全阶段 BI 产出物** | 网易：会用一款 BI 出 ≥3 图仪表盘 | `pyecharts/pyecharts` ⭐15.8k（MIT，半天出图） | `pyecharts/pyecharts-gallery` ⭐1.4k（MIT，抄图表配方）<br>`evidence-dev/evidence` ⭐6947（BI-as-code） | `dataease/dataease` ⭐24444（国产对标 FineBI）<br>`jackchen0120/vueDataV` ⭐2178（MIT，26 个 ECharts 组件）<br>避坑：`iGaoWei/BigDataView`（无许可证） |

---

## 二、第 1 站 SQL（2026-09-17 ~ 11-30）—— P0 第一缺口

### 2.1 零基础第一步（今晚就能开始）：SQL 母网

- **链接**：`http://sqlmother.yupi.icu` ｜ 源码 https://github.com/liyupi/sql-mother（**⭐4388**，push 2025-07，TypeScript）
- **是什么**：程序员鱼皮开源的**闯关式交互式 SQL 自学教程网站**，支持在线 SQL 编辑器、实时查询结果、语法高亮。覆盖 MySQL / SQLite / PostgreSQL 三种方言。
- **为什么放第一步**：**纯网页、零安装、有即时反馈**——对「零基础 + 需要跑通感」的人，这是最短的正反馈回路。今晚就能闯 5 关，明天再装 MySQL 也不迟。
- **核验状态**：**已核验**（⭐4388、push 2025-07-01；站点 `http://sqlmother.yupi.icu` 实测 HTTP 200）。

### 2.2 主线：`civilian7/sql-tutorial` ⭐226 ｜ 最后推送 2026-04

- **链接**：https://github.com/civilian7/sql-tutorial
- **是什么**：自带数据生成器 + 完整教程 + **1065 道练习题（含答案）** 的电商 SQL 练习工程。README 立项目标就是「大多数 SQL 教材有题没数据，这里给你能真正跑起来的数据」。
- **数据与规模**：**无需下载任何外部数据**。自带 Python 造数器，30 张表 / 18 视图 / 5 触发器 / 61 索引；`--size small` ≈ **75 万行、约 80 MB**（medium 700 万行，large 3500 万行）。含 `orders 34,908`、`order_items 84,270`、`product_views 299,792`、`point_transactions 130,149`。
- **一键跑通**：
  ```
  git clone https://github.com/civilian7/sql-tutorial
  cd sql-tutorial && pip install -r requirements.txt
  python -m src.cli.generate --size small                      # 产出 SQLite 库（约 20 秒）
  python -m src.cli.generate --size small --target mysql --apply --ask-password   # 直写 MySQL
  ```
- **技术栈**：SQLite（默认）/ MySQL / PostgreSQL / Oracle / SQL Server **五方言**；生成器 Python；教程 `03-database.md` 已改写为 **Docker Desktop + Docker 建 MySQL 容器**流程（对 Windows 友好）。
- **覆盖技能点**：SELECT/WHERE/ORDER BY、聚合 GROUP BY/HAVING、NULL 语义、**CASE（条件聚合的基础）**、INNER/LEFT JOIN、子查询、UNION/INTERSECT/EXCEPT、DDL/DML、事务、**窗口函数**、**CTE**、EXISTS/反连接、自连接、视图/索引/触发器、JSON、存储过程。练习集含 **Interview Prep / Sales Analysis / Cohort & Customer Segmentation / Analytics** 业务题集。
- **难度**：入门 → 高阶（beginner 240 题 / intermediate 220 题 / advanced 180 题 + 课后复习 270 题）
- **预计耗时**：**3～5 周**（只做主线索 300～400 题，**不要全刷**）
- **怎么用它复现**：
  1. clone + 装依赖 → `--size small` 生成库
  2. 打开 `docs/` 的 MkDocs 教程，按 beginner(00-07) → intermediate(08-17) → advanced(18-26) 顺序学
  3. 每课做完对应 YAML 编译出的题集，**先自己写，再看 `reference_sql`（五方言对照）核对**
  4. 进阶：`--dirty-data` 生成 5-10% 脏数据练清洗（直接对接项目 1 的「数据质量报告」）
  5. **验收**：能独立写出「每个客户每月首单（窗口函数取 Top1）」「CASE WHEN 把订单状态转列做条件聚合」「CTE 做留存率」三类题；`python -m src.verify.verify` 跑官方校验
- **核验状态**：**已核验**（⭐226、push 2026-04-18、fork 49）。抓取确认 `src/exporters/{sqlite,mysql,postgresql,oracle,sqlserver}_exporter.py`、`exercises/advanced-01-window-functions.yaml`(28KB)、`advanced-11-challenge.yaml`(115KB)、`docs/*/playground/ecommerce-playground.db`(1.19MB) 均真实存在。
  - ⚠️ 仓库 description 的「21 lessons / 690K rows」是**旧文案**，README v4.1 才是当前值（27 课 / 75 万行）。
  - ⚠️ 教程为**英文/韩文**双语（SQL 关键词本就是英文，顺带练术语）；中文概念铺底交给 2.3。

### 2.3 补充（中文概念铺底）：`datawhalechina/wonderful-sql` ⭐1091 ｜ 最后推送 2026-08

- **链接**：https://github.com/datawhalechina/wonderful-sql ｜ 国内镜像 https://gitee.com/datawhalechina/wonderful-sql
- **是什么**：Datawhale 出品的**中文**「从 0 到 1 掌握 SQL」任务制课程，基于《SQL基础教程》体系，MySQL 8.0。
- **数据与规模**：自带可执行 SQL 脚本 —— `materials/create_table_sql/shop.sql`（11KB 建表+示例数据）、`world.sql`（**428KB**）、`决胜秋招-建表语句.sql`（9.8KB）。**数据量偏小**（几千行级），不适合练大数据量，但极适合零基础边学边敲。
- **覆盖技能点**：基础查询与排序、聚合与 GROUP BY、视图/子查询/函数/谓词、**CASE 表达式**、集合运算（UNION/INTERSECT/EXCEPT）、**窗口函数**、**GROUPING 运算符 CUBE/ROLLUP**、存储过程、**ch06「决胜秋招」= 中文面试真题**（各部门工资最高、分数排名、连续出现的数字、**行转列/列转行**、**连续登录**、用户购买推荐、**Hive 数据倾斜**、LEFT JOIN 多行问题、ACID、执行计划）。
- **难度**：入门（含进阶内容）｜ **预计耗时**：**2 周**
- **怎么用它复现**：
  1. clone → 按 ch00 装 MySQL
  2. `mysql -u root -p < materials/create_table_sql/shop.sql`、`... < materials/create_table_sql/world.sql`
  3. 逐章读 ch01–ch06，**每章示例 SQL 都必须实际执行**（不要只读）
  4. 做 `practice-questions/question_list.md`，对照各章正文与参考答案
  5. **验收**：能口述并手写「CASE WHEN + SUM 做条件聚合」「ROLLUP 做分组小计」「窗口函数做组内排名 / 累计求和 / 同比环比」
- **核验状态**：**已核验**（⭐1091、push 2026-08-23，是本清单最活跃的中文 SQL 仓库）。抓取确认 `ch00`~`ch06` 章节、`materials/`、`practice-questions/` 全部存在；含 `materials/create_table_sql/{shop.sql, world.sql(428KB), 决胜秋招-建表语句.sql}`。
  - ⚠️ **两个坑**：① **练习题参考答案托管在飞书文档（外部链接）**，且 README 说明「组队学习期间关闭参考答案访问权限」→ 别在组队期死磕；② 仓库**无许可证声明**（`LICENSE` 404）→ 只当学习材料，不要搬运内容进自己的仓库。

### 2.4 补充（练量级）：`datacharmer/test_db` ⭐4440 ｜ 最后推送 2026-04

- **链接**：https://github.com/datacharmer/test_db
- **是什么**：MySQL 官方文档在用的 **employees 示例库**，业界最经典的「大表 SQL 练手底座」。
- **数据与规模**：约 **30 万员工 / 284 万条薪资**，导出数据 167MB。精确行数（README 载明）：`employees 300,024`、`salaries 2,844,047`、`titles 443,308`、`dept_emp 331,603`、`departments 9`。一键导入 `mysql < employees.sql`；**PostgreSQL 版同样自带**（`cd postgresql && bash load_employees_db.sh`）。自带完整性校验（SHA-256，CI 每周跑 MySQL 5.6–9.6 / MariaDB / PG 16/17）。
- **覆盖技能点**：多表 JOIN（employees × dept_emp × departments × salaries）、GROUP BY + 聚合、子查询、自连接（同部门比薪）、分区表 vs 普通表对比、数据清洗（**官方明说数据存在不一致，专门留作清洗练习**）。
- **难度**：入门 → 进阶 ｜ **预计耗时**：**3～5 天**（导入 1 天 + 自造 44 题练 3～4 天）
- **怎么用它复现**：
  1. clone + 起 MySQL 8（本机或 Docker）
  2. `mysql -u root -p < employees.sql` → `mysql -t < test_employees_sha2.sql` **校验六个表行数与 CRC 全 OK 才算导入成功**
  3. 自建题单：每部门薪资 Top3（窗口函数）、每年入职人数、薪资高于本部门均值的人、**男女平均薪资差（条件聚合 `AVG(CASE WHEN gender='M' ...)`）**
  4. **验收**：能在 284 万行 `salaries` 上写出无全表扫描的聚合，并说清「为什么先 GROUP BY 再 JOIN」
- **核验状态**：**已核验**（⭐4440、push 2026-04-10、fork 2703、PLpgSQL）。README 精确行数、`employees_partitioned.sql`、`test_employees_sha2.sql`、`postgresql/load_employees_db.sh` 均确认存在。
  - ⚠️ **它只有数据没有题目** —— 是「练习底座」不是「教程」。

### 2.5 补充（Postgres 专项，按需）：`devrimgunduz/pagila` ⭐1119 ｜ 最后推送 2026-08

- **链接**：https://github.com/devrimgunduz/pagila
- **是什么**：PostgreSQL 版 DVD 租赁示例库（Sakila 的 PG 移植），**仍在活跃维护**（已适配 PG 18/19）。
- **数据与规模**：21 张表，**`payment` 是按月分区表**（覆盖 2022-01 ~ 2026-07）；v4.0 数据刷新后顾客 999 人、rental 约 5.18 万行、payment 约 5.1 万行。
- **一键起环境**：`docker-compose up` 自动建库 + 载数据 + 自带 pgAdmin（http://localhost:5050 ，admin@admin.com / root）。
- **覆盖技能点**：**五表链式 JOIN**（rental→customer→address→inventory→film）、CTE、窗口函数、日期函数、**分区表 + `EXPLAIN ANALYZE` 观察执行计划**、JSONB 操作符、`JSON_TABLE`、全文检索。
- **难度**：入门 → 进阶 ｜ **预计耗时 3～5 天**
- **什么时候用它**：神州 JD 写了「MySQL/PostgreSQL 等数据库」。**如果你想在简历多一个 Postgres 标签**（且面试能讲分区表与执行计划），再开；否则第 1 站不必引入。
- **核验状态**：**已核验**（⭐1119、push 2026-08-06、fork 376）。`docker-compose up` + pgAdmin 默认账号、`pagila-schema.sql`、`scripts/add_monthly_data.sh` 均确认存在。

### 2.6 第 1 站 8 周节奏（嵌入 v2 计划）

| 周次 | 日期 | 主线动作 | 验收 |
| --- | --- | --- | --- |
| 第 1 周 | 09-17 ~ 09-23 | 环境（MySQL 8 + Navicat Lite/DBeaver + Cursor + Docker）+ **SQL 母网起步** + `wonderful-sql` ch00–ch02 | 本地 `SELECT 1` 通；SQL 母网过 20 关；shop/world 建库 |
| 第 2 周 | 09-24 ~ 09-30 | `wonderful-sql` ch03–ch04（视图/子查询/CASE/JOIN/集合运算）+ clone `sql-tutorial` 生成 75 万行库 | ch03–ch04 习题完成；牛客 ≥20 题 |
| 第 3 周 | 10-01 ~ 10-07 | `sql-tutorial` beginner 00–07（英文教程起步） | beginner 题集前半完成 |
| 第 4 周 | 10-08 ~ 10-14 | `sql-tutorial` intermediate 08–12（聚合/JOIN 深化） | beginner 240 题完成 ≥60% |
| 第 5 周 | 10-15 ~ 10-21 | `sql-tutorial` intermediate 13–17 + **`test_db` 导入** | 284 万行表上跑通聚合；intermediate 过半 |
| 第 6 周 | 10-22 ~ 10-28 | `sql-tutorial` **advanced 窗口函数专章** + `wonderful-sql` ch05 | 窗口函数题全过；牛客累计 ≥70 题 |
| 第 7 周 | 10-29 ~ 11-04 | `wonderful-sql` **ch06 决胜秋招**（行转列/连续登录/Hive 数据倾斜） | ch06 全部手写完；力扣数据库 ≥30 题 |
| 第 8 周 | 11-05 ~ 11-14 | `sql-tutorial` Interview Prep 题集 + **条件聚合专题**（自造「每天胜率」） | **口述 3 题 + 手撕 1 题**（限时 10 分钟）通过 |
| 收尾 | 11-16 ~ 11-30 | 牛客累计 ≥100 题 + 力扣 ≥50 题；输出《SQL 核心语法速查》 | 站 1 正式验收（对齐 v2 计划） |

---

## 三、第 2 站 统计推断 / AB 实验 / 指标体系（2026-11-16 ~ 2027-01-10）

> **先说坏消息**：GitHub 上**没有**「高星 + 真实数据 + 完整代码 + 明确结论」的 A/B 实验仓库。高星的（如 ⭐26k 的 pumpkin-book）多是纯公式推导无代码。真正的宝藏在低星区——**而这恰好对您有利**，因为您项目 2 用的 Cookie Cats 数据集，已经有人做出了可直接对答案的完整版本。

### 3.1 主力（对答案用）：`Ali12hamdan/ab-test-cookie-cats` ⭐1 ｜ 最后推送 2026-06

- **链接**：https://github.com/Ali12hamdan/ab-test-cookie-cats
- **是什么**：用 **Cookie Cats 真实实验数据**做的一次教科书级 A/B 全流程分析，统计工具抽成 `src/ab_utils.py` 可复用库——**与您的项目 2 完全同数据集**。
- **数据集**：Kaggle Mobile Games A/B Testing，**90,189 玩家已随仓库提交**（`data/cookie_cats.csv` + 数据字典），**免 Kaggle 账号、无需联网下载**。
- **覆盖技能点（实测逐函数读过源码）**：SRM 卡方检查 ✅、两比例 z 检验 + **差值置信区间** ✅、Bootstrap CI ✅、样本量 / 可检测效应 ✅、**贝叶斯 Beta-Binomial（P(treatment>control) + 期望损失）✅**、CUPED ✅、**比率指标 Delta 方法 / 线性化 ✅**、留存 D1/D7 ✅、实验设计（主指标/护栏/α=0.05/80% power）✅；漏斗 ❌、看板 ❌（这两块正是您项目 2 的增量）。
- **它给出的结论（可直接对照）**：D7 留存 **−0.82pp，95% CI [−1.33, −0.31]，p ≈ 0.0016 → 不上线 gate_40，保留 30 级门**；D1 不显著。SRM 轻微失衡（49.6 / 50.4，p≈0.009）→ **「记录为 caveat 继续分析」** 的活例子。
- **难度**：★★★☆☆ ｜ **预计复现耗时**：**4～6 天**（含自己重写 `ab_utils.py` 里的 3 个函数）
- **怎么用它复现（顺序很重要）**：
  1. 先读 `data/README.md` 与 README 的 TL;DR，记住结论口径
  2. 逐节跑 `notebooks/cookie_cats_ab_test.ipynb`，**先做数据质量**（重复、缺失、49,854 局异常值）
  3. 手写 SRM 卡方复核它报的 49.6/50.4 轻微失衡
  4. 用 `ab_utils.py` 依次跑 z 检验 → bootstrap → 贝叶斯，**比较三者结论一致性**
  5. 自己补一段 **D1/D7 留存漏斗与指标口径说明**（把它从「单实验」扩成您的「指标体系 + 看板」项目）
- **核验状态**：**已核验**（⭐1、push 2026-06-19）。实抓 README + `src/ab_utils.py`（`srm_check`/`two_proportion_ztest`/`bootstrap_diff_ci`/`required_sample_size`/`detectable_effect`/`cuped_adjust`/`ratio_metric_delta_var`/`bayesian_two_proportions` **全部真实存在且实现正确**）+ `data/README.md`（明确写 "A copy is committed here"）。
  - ⚠️ **只有 1 star，无社区背书** —— 所以要用 3.2 的流程模板与 3.3 的真实实验范本交叉印证，别把它当唯一权威。
  - 💡 **它就是「标准答案卡尺」**：您自己先写一遍，再打开它对照——这个方法比直接抄效率高得多。

### 3.2 流程模板（建立「先设计后分析」的骨架）：`Ucazin/ab-testing-framework` ⭐0 ｜ 最后推送 2026-05

- **链接**：https://github.com/Ucazin/ab-testing-framework
- **是什么**：把 A/B 实验全生命周期拆成 **4 个可运行脚本** + 自动生成「上/不上线」决策备忘录（`DECISION_DOC.md`）。是目前找到的**流程最完整**的教学型仓库。
- **数据**：自造合成数据（60,000 用户、双臂、固定种子 42，一键生成）。
- **覆盖技能点**：**样本量 / 功效分析 ✅**、置信区间 ✅、假设检验（两比例 z、Welch t）✅、Bootstrap CI ✅、**SRM 卡方 + AA 检验 ✅**、CUPED ✅、多重比较 BH 校正 ✅、指标体系（转化率/ARPU 双指标 + 护栏）✅、实验设计（MDE、实验时长）✅
- **难度**：★★☆☆☆ ｜ **预计复现耗时**：**2～3 天**（共约 5 小时）
- **怎么用它复现**：
  1. `python src/01_design.py` → 看懂「**先算样本量再开实验**」
  2. `python src/02_simulate.py` → 生成数据，读 `stats.py` 里 `sample_size_two_proportions`（Cohen's h）
  3. `python src/03_validity_checks.py` → 理解 SRM 与 AA 检验为什么是「实验体检」
  4. `python src/04_analyze.py` → 对照 `outputs/DECISION_DOC.md` 学「结论怎么写」
  5. 把 `p_baseline`/`lift` 改成 Cookie Cats 的 19% D7 留存与 0.8pp 落差重跑
- **核验状态**：**已核验**（⭐0、push 2026-05-22）。实抓 README（含真实运行输出：转化 5.49%→6.01%、p=0.0068、SRM p=0.215）+ 实抓 `src/stats.py`（六个函数全部真实存在）。
  - ⚠️ 0 star 新项目。**把它当模板读，不当权威。**

### 3.3 设计文档范本（真实线上实验）：`baumanab/udacity_ABTesting` ⭐84 ｜ 最后推送 2017-05

- **链接**：https://github.com/baumanab/udacity_ABTesting
- **是什么**：Udacity（Google A/B 测试课程体系）对**真实线上实验**的完整分析报告：从指标选择到「不上线」结论到后续实验设计，一份文档全包。
- **数据集**：**真实实验数据随仓库提供**（`data/baseline_vals.csv` + 实验组/对照组每日明细：pageviews、clicks、enrollments、payments）。
- **覆盖技能点**：**不变指标 vs 评估指标的口径设计 ✅**、**dmin（实际显著性阈值）✅**、样本量/功效（α=0.05、β=0.2、MDE=1%）✅、**实验时长与流量权衡（119 天 → 砍掉 retention 指标后 18 天）✅**、Sanity check 用置信区间 ✅、**Sign test ✅**、**Bonferroni 校正的适用性讨论 ✅**、漏斗类转化率（gross/net conversion）✅、留存 ✅
- **难度**：★★★☆☆ ｜ **预计复现耗时**：**2～3 天**（重点不是代码，是**抄它的「设计文档结构」**）
- **怎么用它复现**：① 读 README 的 Experiment Design 段，抄下「不变指标/评估指标」分类逻辑；② 用 `data/` 的真实 CSV 重算 Sanity check（cookie 分配 0.5006 ∈ [0.4988, 0.5012]）；③ 重算 gross conversion 差值 −0.0205 与 CI [−0.0291, −0.0120]；④ 自己补一次 bootstrap 与贝叶斯复核；⑤ 把「**双重显著性（统计显著 + 实际显著 dmin）**」标准写进您 Cookie Cats 项目的结论页
- **核验状态**：**已核验**（⭐84、push 2017-05-13）。实抓完整 README（上述全部数字来自其正文）。
  - ⚠️ **2017 年停更，破了「不推荐停更 3 年」的规则** —— 破例理由：它是**方法论/文档范本**，不是代码依赖；数据是冻结的真实实验数据，不受停更影响。**面试问「实验怎么设计」，照它答就对了。**

### 3.4 游戏业务域（最贴近网易）：`dipanjanchoudhury/mobile-game-retention-analysis` ⭐5 ｜ 最后推送 2026-08

- **链接**：https://github.com/dipanjanchoudhury/mobile-game-retention-analysis
- **是什么**：一款**手游（板球游戏，5 万玩家）的留存与商业化归因案例**：找「为什么流失」并给出最高杠杆的干预方案（含 A/B 实验设计建议）。
- **数据集**：**仓库自带合成数据**（`data/players.csv` 5 万玩家 + `data/sessions.csv` 100,269 场会话 + `generate_data.py`），指标校准到行业基准（**D1 47%、D7 16%、D30 3.5%、付费率 2.1%、top1% 鲸鱼贡献 82.8%**）。
- **技术栈**：Python（pandas）+ **SQL（`queries.sql`，9 个分析查询）** + matplotlib/seaborn + Excel 输出。
- **覆盖技能点**：漏斗（安装→对局→教程→激活→D1/D7/D30）✅、留存 ✅、**渠道归因（安装占比 vs 收入占比错配）✅**、**激活阈值分析（D0 ≥3 局是 D1 留存的断崖点）✅**、指标体系（ARPU/ARPPU/付费率/鲸鱼集中度）✅、**游戏业务 sense ✅**、A/B 实验设计建议 ✅；统计检验 ⚠️（本类最弱项，需自己补）
- **难度**：★★★☆☆ ｜ **预计复现耗时**：**3～4 天**
- **怎么用它复现**：① 跑 `generate_data.py` 造数、`analysis.py` 出图，建立「漏斗 + 留存 + 渠道」三张核心图；② 用 `queries.sql` 第 1–4 条在本地库重算漏斗与周 cohort 留存；③ 把「渠道质量表」改造成您的「版本 × 参与度分层留存表」；④ **抄它的结论写法：每条发现后面跟「最高杠杆动作 + 实验设计（主指标/护栏）」——这正是网易问答题的答题骨架**；⑤ 用它的「条件聚合 + 缺行补零」思路自测
- **核验状态**：**已核验**（⭐5、push 2026-08-13）。实抓 README + 实抓 `queries.sql`（9 段 SQL 真实存在）。
  - ⚠️ **数据是合成生成的**（作者自述按公开手游基准校准）→ **不可当作真实行业基准引用**，只当题型训练器。

### 3.5 归因与留存进阶（按需）

| 仓库 | ⭐ | 最后推送 | 用途 | 怎么用 |
| --- | --- | --- | --- | --- |
| `retentioneering/retentioneering-tools` | 919 | 2026-09 | **用行为路径图做「用户回流归因」**（转移图、Step Matrix、Sankey、漏斗、**diff 模式对比两组路径**） | `pip install retentioneering` → 把 Cookie Cats 转成 `userid/event/timestamp` 事件流 → 用 `diff=[gate_30, gate_40]` 对比两组回流路径 → 导出 HTML 报告进作品集。**这是「用户回流归因」最直观的可视化证据** |
| `CamDavidsonPilon/lifelines` | 2611 | 2026-03 | **留存从「两张百分比表」升级成「留存曲线 + Cox 归因」** | 把 Cookie Cats 改造成 `duration=sum_gamerounds`、`event=是否D7流失`、`group=version` → 画 Kaplan-Meier + log-rank 检验 → 加协变量跑 Cox，看版本系数在控制参与度后是否仍显著 |
| `david26694/cluster-experiments` | 56 | 2026-08 | **样本量 / MDE / 功效曲线 / 比率指标**标准库（pip 可装） | `pip install cluster-experiments` → 用您的 CSV 构 `AnalysisPlan` → 打印 scorecard 的 `ate / ate_ci / p_value` 与手写 z 检验比对 → 用 `mde_time_line()` 回答「实验该跑几天」 |
| `dbt-labs/jaffle_shop_duckdb` | 289 | 2026-03 | **指标体系落到 SQL**（staging → marts → metrics 语义层） | `dbt build` 本地跑 → 把 Cookie Cats 当 `raw_players` 种子表 → 建 `stg_players` → `fct_retention`（D1/D7 指标）→ `metrics`（留存率指标定义）→ `dbt test` 加唯一性/非空测试。**「指标定义在 SQL 里、看板只负责展示」是面试加分项** |

### 3.6 工业界怎么做的（看一眼「真平台」长什么样）

> **专项核查结论**：腾讯、字节、阿里**均无官方开源的 A/B 实验框架**（`abtest org:tencent` / `experiment org:bytedance` / `abtest org:alibaba` 检索结果均为 0）；微软也只有 ⭐15 的小项目。**方法论沉淀在 Kohavi 的书与论文里，不在代码仓。** 下面是可替代的「公司级」开源：

| 仓库 | ⭐ | 最后推送 | 怎么用 |
| --- | --- | --- | --- |
| **`growthbook/growthbook`** | 8377 | 2026-09 | **统计引擎含 CUPED、Sequential、Bayesian、Post-Strat、Bandits、SRM 检查**，自带 Product Analytics 看板，`docker compose up` 自建（MIT + 部分企业目录）。**该看**：docs 里各统计方法的适用说明与 SRM 检查博客——**这是「知道工业界怎么做」的最佳入口** |
| **`FeatureProbe/FeatureProbe`** | 1636 | 2026-06 | 国产团队（自述 5000+ 研发规模内部使用 5 年+），Apache-2.0，含 Toggle 管理、定向规则、流量监控、**Metric Analysis 指标分析 UI**。**该看**：① UI 里「实验如何绑定指标」② targeting 定向规则（**分流怎么实现**）③ 中文文档语境。`docker compose up` 起 |
| `HdShare/WABTest` | 221 | 2026-09 | JVM 微服务 AB 实验，偏工程，活跃 |
| `mozilla/experimenter` | 151 | 2026-09 | Mozilla 官方实验平台（Django）——**看一份真实实验文档长什么样** |
| `CNSRE/ABTestingGateway`（新浪） | 2348 | 2018-10 | AB 测试分流网关（Nginx + Lua/Perl）——**只看架构与分流策略，8 年停更不要复现** |
| ❌ `clklog/clklog` | 188 | 2026-09 | 国产开源埋点平台，但**漏斗分析与留存分析属 PRO 商业版**，社区版没有 |

### 3.7 Cookie Cats 同类仓库的质量对照（**star 高 ≠ 方法全**）

| 仓库 | ⭐ | 最后推送 | 质量点评 |
| --- | --- | --- | --- |
| **`Ali12hamdan/ab-test-cookie-cats`** | **1** | 2026-06 | **本类最佳**（见 3.1）——统计全链路 + 工具库 + 结论 + 边界说明 |
| `HarshSWE6/cookie-cats-ab-test-analysis` | 1 | 2026-09 | 方法论比同类多两步：**功效分析 + 新奇效应检验 + 逻辑回归控制参与度**（OR=0.922，CI [0.884,0.962]，D7 实际功效 0.88）。**只学这两个增量方法**，把它们搬进您的项目做稳健性检验。⚠️ README「How to Run」里写的 `01_explore.py` **实测 404**（与实际仓库不符，以 notebook 为准） |
| `Netcodez/Mobile-Games-A-B-Testing` | 0 | 2024-05 | DataCamp 官方项目 project_184 的**结课答案 notebook**。方法只到 bootstrap——**拿它当「最低配答案」反衬您的增量**（SRM/CI/样本量/贝叶斯/漏斗/看板），面试时这就是「我比课程作业多做了什么」的答案 |
| `ryanschaub/Mobile-Games-A-B-Testing-with-Cookie-Cats` | **23** | **2018-03** | **本类 star 最高，但质量最差之一**：README **仅 6 行游戏介绍，无方法论、无结果、无结论**，方法只到 bootstrap。**star 高 ≠ 方法全**的最好证据 |
| `Jigisha-p/A-B-Testing-Mobile-Game---Cookie-Cat` | 2 | 2024-01 | **实测 `README.md` 返回 404（确无 README）** → **没有 README 的仓库在简历里等于没有说服力**，只当反面清单 |

### 3.8 仓库覆盖不到、必须靠理论学习补齐的三类判断题

> **这一节比上面所有仓库都重要** —— 因为它正好是二面主管最可能追问的地方。

| 面试考点 | 为什么仓库补不上 | 用什么补 |
| --- | --- | --- |
| **「AB 实验样本不平衡怎么办」（二面原题）** | 仓库只能**检测**（SRM 卡方），不能替您回答「怎么办」——**这是判断题不是计算题**。所有仓库只覆盖了「方差缩减」这一支，没有「分流不均衡」的处置流程 | ① **权威依据**：Kohavi, Tang, Xu《Trustworthy Online Controlled Experiments》**第 4 章 Sample Ratio Mismatch**（[experimentguide.com](https://experimentguide.com/)）② Fabijan et al., *Diagnosing Sample Ratio Mismatch in Online Controlled Experiments*（KDD 2019，[ACM](https://dl.acm.org/doi/10.1145/3292500.3330722)）③ **答题骨架（建议背下来）**：**先判性质**（轻微不均衡且 p>0.001 → 记录为 caveat 继续分析；p<0.001 → 停止解读结果）→ **再查三层**（分流层/曝光层/日志层：assignment bug、曝光丢失、埋点丢数）→ **再判可用性**（若为真实流量结构差异：分层/后分层、协变量调整 CUPED、倾向得分加权；若与指标相关则结果不可信）→ **最后决定**（修复重跑，或按预设护栏指标降级采信）。**3.1 里 p≈0.009 的轻微失衡正是「记录 caveat 继续分析」的活例子** |
| **「置信区间计算」（笔试）** | 仓库只给 `proportion_confint` 调用，**不解释** Wald vs Wilson vs Bootstrap 的差别与适用条件 | ① [statsmodels 官方 `stats.proportion` 文档](https://www.statsmodels.org/stable/stats.html#confidence-intervals)（含 `proportion_confint` 的 method 参数）② ThinkStats2 Ch.8–9 手推 ③ **面试口径**：小样本/极端比例用 Wilson 或 Clopper-Pearson；**报告里给「差值 CI」而不是「两个率各自的 CI」** |
| **「贝叶斯条件概率计算」（笔试）** | Cookie Cats 仓库只给贝叶斯 AB 的**代码结果**（P(T>C)、期望损失），**不给概率题的推导训练** | ① **ThinkBayes2**（⭐2080，活跃，免费在线）：Ch.1–2 把「曲奇问题/骰子问题」手算熟练 ② PPL-Bayesian-Hackers（⭐28190）Ch.1–3 ③ 决策口径参考 GrowthBook 文档的 Bayesian + expected loss |
| 指标体系设计（北极星/AARRR/漏斗口径/**OEC**） | 没有任何仓库教您「该选哪个指标」，仓库只会算您让它算的 | ① Amplitude《North Star Playbook》（免费）② AARRR 原始框架（Dave McClure, 2007）③ **Kohavi 书中的 OEC（Overall Evaluation Criterion）章节** ④ 中文读物 `DSXiangLi/Paper_CausalInference_abtest`（⭐252，2023-03，**纯笔记无代码，仅作读物**） |
| 用户回流/留存归因（问答题，需真实游戏例子） | 代码能算留存曲线与渠道差异，但「**归因逻辑**」（是渠道质量、活动刺激、还是产品改动？）需要方法论 | ① `lifelines` 做生存分析与 Cox 系数 ② 归因方法论：渠道归因/Shapley 值、**增量（uplift）建模与增量实验** ③ 游戏例子直接用 3.4 的「渠道质量 × 激活阈值」结论讲故事 ④ 中文因果推断入门《Causal Inference: The Mixtape》（[mixtape.scunning.com](https://mixtape.scunning.com/)） |
| FineBI / PowerBI（商业软件） | 两家**均无开源仓库** | ① FineBI 官方有**免费个人版**可直接练 ② 用 **DataEase**（⭐24444）+ **Evidence** 做等价作品 ③ PowerBI Desktop 免费，配 Olist 真实电商数据练 DAX |
| 游戏业务 sense（DAU/MAU/付费率/ARPPU/LTV/回流窗口） | 仓库给的是单次分析，**不给品类基准值与术语体系** | ① 3.4 项目里校准到行业基准的指标（D1 47%/D7 16%/付费率 2.1%/ARPU $0.196）可作参照 ② Sensor Tower / data.ai / Newzoo 免费摘要 ③ **把术语写成您项目里的「指标字典」一页，面试可直接展示** |

**跑通顺序（照这个走，不要在仓库之间乱跳）**：
```
Ucazin（2h，建立「先设计→再体检→后分析→出决策」骨架）
  → Ali12hamdan（逐节跑通，每节自己先手写再对答案）
  → 默写 ab_utils.py 的 4 个函数（srm_check / two_proportion_ztest / bayesian_two_proportions / cuped_adjust）← 白板题常考
  → cluster-experiments（复核样本量：「若 MDE 只有 0.5pp，需要多少用户、跑多久」）
  → dipanjanchoudhury + retentioneering（补漏斗 + D1/D7/D30 留存 + 分层归因）
  → Evidence / DataEase（出看板）+ lifelines（加留存曲线）
  = notebook + 看板 + 结论文档 三件套齐 → 上简历
```

### 3.9 统计理论基础（笔试考计算的部分）

| 仓库 | ⭐ | 最后推送 | 补什么 |
| --- | --- | --- | --- |
| **`AllenDowney/ThinkBayes2`** | 2080 | **2026-09（活跃）** | **贝叶斯条件概率手算（笔试原题）**：Ch.1–2 把「曲奇问题/骰子问题」手算熟练 → Beta-Binomial 章节把 Cookie Cats 的 D7 留存当 `Beta(1+留存数, 1+未留存数)` 更新后验 → 算 `P(gate_30 优于 gate_40)` 与期望损失，与 3.1 的 `bayesian_two_proportions` 对照。**免费在线。** |
| `AllenDowney/ThinkStats2` | 4231 | 2025-01 | **置信区间的推导与重采样**：只做 Ch.7–9（分布、假设检验、置信区间）→ 手推一次「比例的标准误公式」→ 用它的 `Resample` 工具对 Cookie Cats 做**置换检验**（不依赖公式验证 z 检验结论）→ 面试能讲「我用两种方法交叉验证」 |
| `CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers` | 28190 | 2024-06 | 贝叶斯 A/B 测试 + 流失建模章节（PyMC）。⚠️ 书中多为 PyMC3 旧语法，需对照 `pymc-devs/pymc`（⭐9755）改写——**踩这个版本坑本身就是好的工程训练** |
| `statsmodels/statsmodels` | 11629 | 2026-09 | 上述所有仓库的底层依赖。**只精读 `stats.proportion` 与 `stats.power` 两个模块的文档**（`proportion_confint` 的 Wald/Wilson/Clopper-Pearson 差别） |

> ⚠️ 不算推荐项但值得一读：`DSXiangLi/Paper_CausalInference_abtest`（⭐252，2023-03）—— 中文因果推断与 AB 实验论文笔记，**纯笔记无代码**。

### 3.7 第 2 站 8 周节奏

| 周次 | 日期 | 内容 | 用哪个仓库 | 验收 |
| --- | --- | --- | --- | --- |
| 第 1-2 周 | 11-16 ~ 11-29 | 描述统计、抽样分布、置信区间、假设检验（t/卡方/两比例） | `ThinkStats2` Ch.7–9 | 手推标准误公式；自编置信区间题 ≥5 道 |
| 第 3 周 | 11-30 ~ 12-06 | 贝叶斯条件概率 + Beta-Binomial（**笔试原题**） | `ThinkBayes2` Ch.1–2 + Beta-Binomial 章 | 能纸上手算条件概率题；真题模拟正确率 ≥80% |
| 第 4-5 周 | 12-07 ~ 12-20 | **AB 实验全流程**：假设→指标选择→样本量→分流→显著性→结论 | `Ucazin`（流程骨架）→ `Ali12hamdan`（对答案） | **AB 实验方案 2 份**成文（含样本不平衡处理方案） |
| 第 6-7 周 | 12-21 ~ 2027-01-03 | 指标体系与业务拆解（北极星/漏斗/留存/AARRR/归因） | `dipanjanchoudhury` + `retentioneering` | 拆解笔记 ≥5 篇（如「某游戏 DAU 下降 10% 怎么分析」） |
| 第 8 周 | 01-04 ~ 01-10 | 实验设计文档 + 结论口径 | `baumanab`（抄文档结构） | 能口述「p 值与置信区间」「留存怎么做」各 1 分钟（录音自查） |

---

## 四、第 3 站 数仓分层 + 大数据生态（2027-01-11 ~ 01-31，概念级）

> **本节的中心判断**：这一站的仓库要**严格分三档**——「能跑的」（当练习场）、「该读的」（抄规范与话术）、「别碰的」（会耗掉你一整周去搭环境然后失败）。

### 4.1 主线（中文速查手册）：`heibaiying/BigData-Notes` ⭐16,969 ｜ 最后推送 2024-01

- **链接**：https://github.com/heibaiying/BigData-Notes
- **是什么**：中文圈最知名的《大数据入门指南》，12 大模块的**纯文档笔记**仓库（**不是可运行工程**，545 commits / 9 committers）。
- **覆盖内容**：Hadoop（HDFS/MapReduce/YARN/单机+集群搭建/HDFS Shell 命令/HDFS Java API/高可用）、**Hive**（简介/安装/CLI 与 Beeline/DDL/**分区表与分桶表**/视图与索引/DML/数据查询详解）、**Spark**（RDD/算子详解/运行模式与提交/累加器广播变量/**Spark SQL DataFrame**/聚合函数/JOIN/Streaming 与 Flume、Kafka 整合）、Storm、Flink、HBase、Kafka、Zookeeper、Flume、Sqoop、Azkaban、Scala。
- **为什么是主线**：**神州面经的原题全在这里**——「数仓分层理解」「Hive 与 Spark SQL 的区别」「分区表与分桶表」；中文、体系全、当速查手册读最快。
- **难度**：入门（阅读型）｜ **预计耗时**：**1 周泛读**（只读 Hive + Spark + Hadoop 三块）
- **怎么用它复现**：**不要 clone 通读**。按需打开对应 `notes/*.md` → 对照产出您的《数仓分层 + 大数据生态速记卡》10 张 → 录音自查「Hive vs Spark SQL」1 分钟
- **核验状态**：**已核验**（⭐16,969，ungh 实时；ecosyste.ms 16,422 为 2025-05 过时快照；shields 复核 17k ✓；push 2024-01-05）
  - ⚠️ **它是纯笔记，帮不了您「复现」任何东西** —— 定位是「速查手册」，不是「项目」。
  - ⚠️ **无许可证** → 只读不搬运。
  - ⚠️ **别再找 `zhengzebiaodashi/BigData-Notes`**：该用户 GitHub 上 **0 个公开仓库**，此路径从未存在（本清单已反查纠正）。

### 4.2 唯一确定能跑完的分层数仓：`DataWithBaraa/sql-data-warehouse-project` ⭐952 ｜ 最后推送 2025-04

- **链接**：https://github.com/DataWithBaraa/sql-data-warehouse-project
- **是什么**：一个完整可跑的「现代数仓 + 分析」作品集项目（英文）：CSV 源数据 → SQL Server 数仓 → 星型模型报表。
- **架构与分层**：**Medallion 三层 Bronze / Silver / Gold**，等价于 ODS/DWD/ADS：Bronze 原样落库 → Silver 清洗标准化 → Gold 星型模型（事实 + 维表）。目录即分层：`scripts/bronze/`、`scripts/silver/`、`scripts/gold/`、`tests/`，另有 `docs/naming-conventions.md`、`data_catalog.md`、`data_models.drawio`（星型模型图）、`data_architecture.drawio`。
- **技术栈**：纯 **SQL（TSQL）/ SQL Server Express + SSMS**，**无 Spark/Hive/Docker 依赖**，含 `datasets/` 真实 ERP+CRM CSV。
- **跑起来的门槛**：**⭐（最低门槛）**。Windows 原生装 SQL Server Express + SSMS 即可，或 WSL2 起 `mcr.microsoft.com/mssql/server` 容器。
- **覆盖技能点**：ETL 分层（Bronze/Silver/Gold + 星型/雪花，**强**）｜数据质量校验（`tests/` 有质量校验脚本，**有**）｜调度（无，纯手跑）｜监控（无）｜Linux/Shell（无）
- **难度**：低 ｜ **预计复现耗时**：**15～20 小时**（**这是本节唯一您 100% 确定能从头跑完的仓库**）
- **怎么用它复现**：
  1. clone → 读 `README.md` 与 `docs/requirements.md`，抄它的**分层职责定义**与 `docs/naming-conventions.md` 命名规范
  2. 起 SQL Server → 按 `scripts/bronze/` → `silver/` → `gold/` 顺序执行，导入 `datasets/` 的 CSV
  3. 跑 `tests/` 的质量校验脚本，看它如何用 SQL 断言「主键唯一 / 必填非空 / 金额非负 / 两表口径一致」——**这套写法直接搬进您项目 3 的质量校验报告**
  4. 打开 `docs/data_models.drawio` 学星型模型画法，照着给日志项目画一张
  5. **改造点**：把表结构换成日志主题（访问事实表 + 时间/URL/状态码/UA 维表），SQL 全部改写成 Spark SQL → 得到您项目 3 的 DWD/DWS 层雏形
- **核验状态**：**已核验**（⭐952、push 2025-04-23）。README 全文确认 Bronze/Silver/Gold 定义、`scripts/{bronze,silver,gold}`、`tests/`、`datasets/` 均出自原文。
  - ⚠️ **风险标注：中高** —— README 下半部分是完整的**课程引流闭环**（YouTube、`datawithbaraa.com`、Substack、PayPal 打赏、多个 Course Link）。**代码与数据集是完整且免费的**，当纯代码仓库用没问题，别被引流带走。

### 4.3 读架构（别硬跑）：`MrSuiChuan/data-warehouse-learning` ⭐1243 ｜ 最后推送 2026-04

- **链接**：https://github.com/MrSuiChuan/data-warehouse-learning ｜ 上游 `https://github.com/Mrkuhuo/data-warehouse-learning` ｜ Gitee 镜像 `gitee.com/wzylzjtn/data-warehouse-learning`（667★）
- **是什么**：中文圈最热的《实时/离线数仓实战》。以电商业务指标需求驱动，走 **ODS → DWD/DIM → DWS → ADS** 四级分层，Doris SQL / FlinkSQL 实现。
- **⚠️ 必须先纠正一个普遍误解**：**它是「文档 + 截图 + 一个 pom」型仓库，不含可一键运行的数仓代码**。实测根目录只有 `src/main`（里面几乎全是 `images/*.png`）、`LICENSE`、`README.md`、`pom.xml`，34MB 体积几乎全是图片。
- **技术栈（看清门槛）**：Kafka 3.6.1、Flink 1.18.1、Doris 2.0.4、Paimon/Hudi/Iceberg、SeaTunnel 2.3.3、DolphinScheduler 3.2.0、Dinky、Hive 3.1.3、Hadoop 3.1.3、**CentOS 8 + OpenJDK 8 + Maven 3.9.6**（15 个组件，目标环境是服务器集群）。
- **跑起来的门槛**：**⭐⭐⭐ 必须整套集群，笔记本不可能** → **定位：只能读**。
- **正确用法（读架构，不硬跑）**：
  1. **不要 clone 后试图搭建**
  2. 精读 README 的 Doris 离线部分第 2–6 节，把 ODS/DIM/DWD/DWS/ADS 每一步的**输入输出、加工粒度、表命名**抄成您的**分层设计表**
  3. 对照读实时部分（Paimon/Hudi/Iceberg 同层实现），理解「**同一业务逻辑、不同技术实现**」——这是面试「为什么这么分层」的现成话术
  4. 把它「ADS 层做报表/大屏」的思路，替换成您项目里的「质量校验报告 + 指标查询」
  5. **想要真跑，用它的降级版**：Doris 换 MySQL、Flink 换 Spark、DolphinScheduler 换 cron
- **核验状态**：**已核验**（⭐1243、push 2026-04-26、fork=false、Artistic-2.0）。README 全文（分层说明 + 15 组件版本表 + **安装/ODS/DWD/DWS/ADS 全部为图片引用**）+ Gitee 页面（667★/188 fork/266 commits，根目录仅 4 项）。
  - ⚠️ **fork 陷阱**：GitHub 上有**多个 0 star 的同名 fork**（如 `big-data-open-source/data-warehouse-learning`，创建 2025-07、无独立价值）。认准 ⭐1243 的 `MrSuiChuan` 版或上游 `Mrkuhuo`。

### 4.4 抄分层规范（读文档不跑集群）：`Smars-Bin-Hu/EComDWH-BatchDataProcessingPlatform` ⭐173 ｜ 最后推送 2025-10

- **链接**：https://github.com/Smars-Bin-Hu/EComDWH-BatchDataProcessingPlatform
- **是什么**：一个人的「企业级离线电商数仓」完整工程：数仓建模 + 自建分布式大数据平台 + PySpark 批处理 + Airflow 调度 + 监控 + BI。**中文作者、英文文档、MIT。**
- **架构与分层**：**真分层且最全** —— `ODS / DWD / DWM / DWS / DWT / ADS` **六层 + DIM 维表层**，明确星型/雪花建模。文档含《数仓分层规范》《表命名规范》《分区列命名规范》《表生命周期管理规范》《数仓建模 SOP》+ 业务调研文档 + 架构图 + **13 篇排错记录**。
- **跑起来的门槛**：**⭐⭐⭐**。`docker-compose-bigdata.yml` 共 10 个服务（hadoop-master/worker1/worker2、mysql、hive、spark、oracle、airflow、monitoring），官方 quick-start 明写推荐 **CPU 10 核、内存 16GB、磁盘 240GB**；且 OLAP 用 Azure 云 ClickHouse（要换或砍）。
- **正确用法（**抄规范与代码结构，不跑集群**）**：
  1. 只 clone 不 `compose up` → 读 `docs/doc/data-warehouse-development-specification/` 四份规范，写成您自己的《日志数仓分层与命名规范》
  2. 读 `src/warehouse_modeling/`（Hive DDL，含 ods/dwd/dwm/dws/dwt/dim 各层建表），挑日志项目要用的表结构改写成 Spark SQL DDL
  3. 读 `src/batch_processing/jobs/{ods_to_dwd,dwd_to_dim,dwd_to_dwm,dwm_to_dws}.py` 这条链，学「**一作业一文件 + 统一入口 `main_batch_processing.py`**」的组织方式，用 PySpark `local[*]` 重写
  4. 读 `src/scheduler/dags/dag_batch_process.py` + `utils/build_spark_submit_command.py` 学 DAG 怎么拼 `spark-submit`；不装 Airflow 就降级成 `run_pipeline.sh` + cron
  5. **读 `docs/doc/error-handling/` 那篇「Git 换行符转换导致 JournalNode/NameNode 启动失败」** —— 这正是您在 WSL2 写 `.sh` 必然踩的 **CRLF 坑**，提前配好 `.gitattributes` 与 `git config core.autocrlf`
- **核验状态**：**已核验**（⭐173、push 2025-10-07、MIT）。实读 `docker-compose-bigdata.yml`（364 行，10 服务）、`src/README/quick-start.md`（「16GB 内存 / 240GB 磁盘 / 10 核 / Windows 用 git bash」原文）；jsDelivr 全量 **369 个文件清单**（sh=67、py=62、hql=42、sql=27、md=48），确认各层 DDL 与作业脚本真实存在。

### 4.5 读业务 SQL（只读，别跑）：`lhq-123/Spark-Flink-DataWarehouse` ⭐46 ｜ 最后推送 2023-01

- **链接**：https://github.com/lhq-123/Spark-Flink-DataWarehouse
- **价值在哪**：**它的离线链路是一份完整的分层数仓代码树，SQL 极对口神州考点**：
  - `项目代码/SparkOffline/SparkApplication/1_ods/ddl/B_Full.sql`(10KB)、`2_dim/`
  - `3_dwd/ddl/fact_ddl.sql`（**61KB**，事实表 DDL）
  - `4_dws/`（历史至今 / 近 N 日 / 当日三种汇总）
  - **`5_ads/` 有漏斗分析、留存、复购率、用户变化、品类交易等真实业务 SQL** ← **这一块直接对应您项目 2 的指标与神州面经**
  - `6_report/datax/*.sh` + `mysql/bi.sql`(17KB)、`Wrapper.py`（Shell/Python 调度）
  - `模拟数据/gmall.sql`(221KB 业务库 DDL) + 造数 jar
- **致命缺陷**：**停更 3 年 8 个月**、**无许可证**、**根目录多个文档是 0 字节空壳**（`5-数据建模(DWD).md`、`6-数据建模(DWS).md`、`7-数据建模(ADS).md`、`7-1 项目测试记录.md`）、README 仅 3 行、跑通需 Hadoop+Hive+Spark+Kafka+Flink+ClickHouse+MySQL 全家桶。
- **正确用法**：**只读 `5_ads/*.sql`（漏斗/留存/复购）和 `3_dwd/ddl/fact_ddl.sql`（分层 DDL 写法）**，把逻辑抄进项目 3。**绝不要尝试在本地跑通。**
- **核验状态**：**已核验**（⭐46、push 2023-01-28、Java、无许可证）。文件树逐条确认含上述路径与 0 字节文档；包名 `com.atguigu.gmall2020`（尚硅谷 gmall 衍生）。

### 4.6 想摸一次「真 Hive」（可选，4～6 小时）

| 仓库 | ⭐ | 最后推送 | 说明 |
| --- | --- | --- | --- |
| `big-data-europe/docker-hive` | 1081 | 2024-06 | **在笔记本上真起一套 Hive 的唯一成熟 Docker 方案**。`docker-compose up -d` 起 6 个服务（namenode、datanode、hive-server:10000、hive-metastore:9083、metastore-postgresql、presto:8080）。按 README 跑 beeline 冒烟测试（`CREATE TABLE pokes` + `LOAD DATA`）→ 然后把 4.3/4.5 的分层 DDL 改成日志主题**在真 Hive 上跑一遍建表与分区** → 用 `EXPLAIN` 对比 Spark SQL 的 `EXPLAIN`——**这就是「Hive 与 Spark SQL 的区别」面经题的实证素材**。⚠️ 版本老（Hive 2.3.2 / Hadoop 2.7.4），默认分支最后提交约 2019-05 |
| `big-data-europe/docker-hadoop` | 2325 | 2024-02 | HDFS + YARN 五容器版。**必须先改小 `hadoop.env` 的内存值**（默认 `yarn_nodemanager_resource_memory_mb=16384` / map 4096 / reduce 8192 → 按默认值跑 wordcount 要 16GB 级内存）。`make wordcount` 是理解 HDFS/YARN 最快的路径 |
| `cluster-apps-on-docker/spark-standalone-cluster-on-docker` | 510 | 2025-11 | 一条命令起 **Spark Standalone + JupyterLab**（`localhost:8888` / Driver UI `localhost:4040`）。当作项目 3 的**本地开发环境**：写出 `ods_to_dwd.py` 后 `spark-submit --master spark://spark-master:7077` 提交，比 `local[*]` 更接近真实 |

### 4.7 补充（中文概念阅读）：`datawhalechina/juicy-bigdata` ⭐363 ｜ 最后推送 2025-08

- **链接**：https://github.com/datawhalechina/juicy-bigdata
- **内容实质（已实测文件树）**：`docs/` 是 10 章 markdown 教程（ch01 概述、ch02 Hadoop、ch03 HDFS、ch04 HBase、ch05 MapReduce、ch07 Hive、ch08 Spark…，正文约 300KB）+ **几百张截图**；`experiments/` 是分章实验文档（含 **Hive 数仓：桶表/分区表/导入导出**、Spark SQL / PySpark RDD）。**真正的代码只有 4 个 Python 作业模板**（各 1.4–2KB）。
- **评价**：**文档为主体，跑不了**（README 要求 Java 8 + Hadoop 3.3.1 + HBase 2.3.5 + Hive 2.3.9 + Spark 3.2.0 + MySQL 8，且安装包走飞书网盘+提取码）。
- **怎么用**：当**中文概念的补充阅读**（尤其 `docs/ch07-Hive.md` 47KB 与 Hive 分区表/分桶表实验步骤），**不要照它装环境**——用 4.6 的 Docker 版更省时间。
- **核验状态**：**已核验**（⭐363、push 2025-08-29；jsDelivr 文件树确认**无 docker-compose、无 requirements.txt**）。

### 4.8 第 3 站 3 周节奏

| 周次 | 内容 | 用哪个仓库 | 验收 |
| --- | --- | --- | --- |
| 第 1 周 | 数仓分层与建模（ODS/DWD/DWS/ADS、星型/雪花、事实/维度表） | `BigData-Notes` + `MrSuiChuan` 架构图 + `EComDWH` 四份规范 | 《数仓分层速记卡》四层职责 + 星型/雪花图解 |
| 第 2 周 | ETL 与数据治理（全链路、质量六维度、指标口径、血缘） | `DataWithBaraa`（**动手跑**）+ `EComDWH` | 跑完 Bronze/Silver/Gold 三层；质量六维度自查清单（每维度 2 个检查 SQL） |
| 第 3 周 | 大数据生态（HDFS/YARN/MapReduce/Hive/Spark/Flink/Kafka 一句话角色、批 vs 流、Hive vs Spark SQL） | `BigData-Notes`（Hive + Spark）→ 可选 `docker-hive` 摸真 Hive | 10 张组件速记卡 + 录音自查「Hive vs Spark SQL」1 分钟 |

---

## 五、第 4 站 ML + 游戏数据分析 + 大模型（2027-02）

### 5.1 ML 原理（面试概念）

| 仓库 | ⭐ | 最后推送 | 用途与用法 |
| --- | --- | --- | --- |
| `LongxingTan/Machine-learning-interview` | 336 | 2026-05 | **机器学习/数据科学家面试指南（中文）**。直接对接网易一面考点：随机森林、逻辑回归原理、特征筛选、评价指标（准确率/召回率/F1/AUC）。**做法：把面试题当题库，每题写 30 秒口头作答版 → 汇总成您的《ML 面试概念卡》≥20 张** |
| `datawhalechina/hands-on-data-analysis` | 1531 | 2024-05 | Datawhale「动手学数据分析」：每个部分分**课程 + 答案两套 notebook**，覆盖 pandas 载入/EDA、数据清洗与特征处理、数据重构、可视化、sklearn 建模与评估。**这是唯一「自己敲一遍再对答案」的 pandas 练习册** → 直接复用您的 pandas 底子，产出可写进简历的分析流程。⚠️ push 2024-05（未超 3 年线）；**无标准 LICENSE 文件**，README 声明 CC BY-NC-SA 4.0 |
| `AllenDowney/ThinkStats2` | 4231 | 2025-01 | 见 3.6：重采样/置换检验 |

### 5.2 游戏指标拆解（笔试游戏常识 + 面试游戏理解）

| 仓库 | ⭐ | 最后推送 | 怎么用 |
| --- | --- | --- | --- |
| `dipanjanchoudhury/mobile-game-retention-analysis` | 5 | 2026-08 | 见 3.4。**它的「渠道质量 × 激活阈值」结论与「发现 → 最高杠杆动作 → 实验设计」写法，就是问答题的答题骨架**；指标基准（D1 47%/D7 16%/付费率 2.1%/top1% 贡献 82.8%）可作参照（合成数据，勿当真实基准引用） |
| `retentioneering/retentioneering-tools` | 919 | 2026-09 | 见 3.5。`diff` 模式对比两组行为路径 → 「用户回流归因」的可视化证据 |
| `imburaktas/mobile-game-analytics` | 1 | 2026-01 | 手游分析：留存 + A/B 测试 + 流失预测 + Streamlit 看板。**参考价值**（小仓库，看它的看板组织） |

### 5.3 大模型辅助分析（**JD 第 2-3 条直接命中，原计划漏项**）

- **`microsoft/data-formulator` ⭐17,254 ｜ 最后推送 2026-09（微软研究院，活跃）**
  - **链接**：https://github.com/microsoft/data-formulator
  - **是什么**：LLM 驱动的数据分析/可视化工具——**用自然语言迭代生成数据转换与图表**。技术栈：Python + TypeScript/React + LLM API（可接自己的模型）。
  - **为什么这是「JD 直接命中」**：网易 JD 第 2-3 条要求「引导 AI 完成数据处理与计算，**审核并优化 AI 产出结果**」「沉淀分析 Prompt 库、指标解读模板」。这个工具**生成的 pandas 代码可读可改**——正好是「审 AI 产出」的实操场景。
  - **怎么用它复现**：
    1. 本地起服务后上传 `cookie_cats.csv`
    2. 用自然语言让它生成「按 version 分组的 D1/D7 留存柱状图」与「参与度分布」
    3. **重点：逐个核对它生成的代码与统计口径是否正确**（面试常问「AI 给的结论你敢直接用吗」）
    4. 把「AI 出图 + 人工复核统计口径」写成一段工作流说明，并入您的「AI 辅助分析实例」（对齐 v2 计划站 4 验收动作 3：≥2 个成文实例）
  - **核验状态**：**已核验**（⭐17,254、push 2026-09-18、Python）。内容描述基于其公开产品定位（README 未逐行读取）。
  - 💡 **配合您的「AI 辅助写 SQL」留档**：站 1 起每次记录「我让 AI 做了什么 + 我校验了什么」，到站 4 整理成 2-3 个完整案例——**这条线现在有工具支撑了**。

---

## 六、三个简历项目的参考项目组合

### 6.1 项目 1：光伏购电优化（2027-01-11 ~ 02-28）

| 模块 | 参考仓库 | 借什么 | 核验 |
| --- | --- | --- | --- |
| **线性规划决策优化** | `samirsaci/supply-planning` ⭐16 ｜ push 2026-09-17 | **PuLP 线性规划的标准写法**：目标函数、约束、求解、结果可视化。作者另有 `budget-planning`（⭐15）、`workforce-planning`（⭐14）同模式，**三个一起看能快速摸清「业务问题 → 线性规划」的建模套路** | 已核验（三家均 ⭐14-16、push 2026-09-17） |
| **光伏功率预测** | `shengwei-peng/PV-Power-Generation-Forecasting` ⭐23 ｜ push 2025-03-10 | 用区域微气候数据做光伏预测的特征工程与模型实现（中文作者，Jupyter） | 已核验 |
| **数据源** | Kaggle「Solar Power Generation Data」（`Plant_1_Generation_Data.csv` + `Plant_1_Weather_Sensor_Data.csv`） | 出力与气象数据 | **已核验 HTTP 200**（`kaggle.com/datasets/anikannal/solar-power-generation-data`） |
| **负荷数据** | UCI「Individual household electric power consumption」 | 家庭用电负荷曲线 | **已核验：静态 zip 可直下**（`archive.ics.uci.edu/static/public/235/...zip`，实测 **20,640,916 字节**，**无需登录**）← 比 Kaggle 省事 |
| **数仓分层** | 见第四节 4.2 `DataWithBaraa` | 分层职责与命名规范 | — |
| **BI 看板产出** | `pyecharts` ⭐15.8k（MIT） | 3 图 HTML 看板 | 见 6.4 |

> 💡 **一个实操提醒**：Kaggle 数据集下载**可能需要账号登录**。若下载不顺，优先用上面已实测可直接下载的 UCI 静态 zip；或按计划里的备选「用 numpy 生成仿真负荷曲线并在 README 声明」。

### 6.2 项目 2：移动游戏 AB 实验与留存分析（MVP 2027-02-08 ~ 02-28）

| 模块 | 参考资源 | 借什么 |
| --- | --- | --- |
| **主数据** | Kaggle「Mobile Games A/B Testing」（Cookie Cats） | **已核验 HTTP 200**（`kaggle.com/datasets/yufengsui/mobile-games-ab-testing`）；数据集 2.8MB、9 万+ 玩家。**备选：`Ali12hamdan/ab-test-cookie-cats` 仓库里已随附 `data/cookie_cats.csv`（90,189 玩家）→ 免 Kaggle 账号** |
| **AB 全流程与统计方法（对答案）** | `Ali12hamdan/ab-test-cookie-cats` ⭐1 | SRM / z 检验 / 差值 CI / Bootstrap / 贝叶斯 / CUPED / Delta 方法的完整实现（**先自己写，再对答案**） |
| **流程骨架** | `Ucazin/ab-testing-framework` ⭐0 | 「先设计（样本量）→ 再体检（SRM/AA）→ 后分析 → 出决策」四步脚本结构 |
| **结论与设计文档写法** | `baumanab/udacity_ABTesting` ⭐84 | 不变指标/评估指标口径、dmin 双重显著性、实验时长权衡 |
| **漏斗 / 留存 / 业务叙事** | `dipanjanchoudhury/mobile-game-retention-analysis` ⭐5 | 漏斗与 cohort SQL、渠道归因、**「发现 → 最高杠杆动作 → 实验设计」的结论骨架** |
| **回流归因可视化** | `retentioneering/retentioneering-tools` ⭐919 | `diff` 模式对比两组行为路径 → 留存归因的图证 |
| **留存曲线进阶** | `lifelines` ⭐2611 | Kaplan-Meier + log-rank + Cox（把留存从百分数升级成曲线 + 归因系数） |
| **指标体系落到 SQL** | `dbt-labs/jaffle_shop_duckdb` ⭐289 | staging → marts → metrics 语义层；「指标定义在 SQL 里、看板只负责展示」 |
| **扩展数据（完整版）** | Kaggle「Steam Store Games」 | **已核验 HTTP 200**（`kaggle.com/datasets/nikdavis/steam-store-games`） |
| **降级预案** | — | 若 Kaggle 下载受阻：`Ali12hamdan` 仓库内 CSV 直接可用（见上） |

> **本项目的战略定位**：这一站开源仓库普遍薄弱，**所以您的项目 2 是「补空白」而不是「复现」** —— 这也正是它在简历上的价值：您做的不是「又一个 Kaggle 作业」，而是**补齐了公开资源里缺失的「游戏 AB + 留存 + 指标体系 + 看板」全链路**。

### 6.3 项目 3：日志 ETL 管道（2027-05-01 ~ 06-30）

**架构参考来源组合（一个模块一个来源）**

| 您的模块 | 从哪个仓库借 | 借什么 |
| --- | --- | --- |
| **日志解析 + Spark SQL 入门** | **`databricks/LearningSparkV2` ⭐1405** | **`chapter7/` 自带 22MB 真实 Web 访问日志**（`web1_access_log_20190715-064001.log`）+ `config/log.cfg`；对照 `SortMergeJoin_7_6`、`CachingData_7_5`、`Partitions_7_2` 练「日志解析 + 缓存 + 分区 + 排序合并连接」。**NASA 日志格式与它同构**（`host - - [date] "GET url HTTP/1.0" status bytes`）→ **门槛 ⭐（装 JDK + Spark 即可，零容器零集群）** |
| **分层 ETL 骨架 + Makefile 一键入口** | **`josephmachado/efficient_data_processing_spark` ⭐393** | capstone 的 `etl/{bronze,gold,interface}/` 结构（含 `clickstream.py` **与您的日志主题同构**）+ `Makefile` 的 `make setup` / `make spark-sql` / `make rainforest` / `make pytest` 目标设计 → **改写成您的 `run_pipeline.sh`**。⚠️ 门槛 ⭐⭐（Docker + WSL2，官方 README 明确支持 WSL，`--scale spark-worker=2`） |
| **调度 + 报告产出** | `josephmachado/beginner_de_project` ⭐594 | 一条 `make up` 起 Airflow + Postgres + DuckDB + Spark + MinIO（**只要 4GB 内存**，全装在同一容器）；`dags/scripts/dashboard/dashboard.html` 学「跑完自动出报告」。**不装 Airflow 就降级成 `run_pipeline.sh` + cron** |
| **采集层 Shell 写法** | `DataTalksClub/data-engineering-zoomcamp` ⭐45607 | **只取一样**：`06-batch/code/download_data.sh` 的 bash 循环下载 + `set -e` + 解压的健壮写法。⚠️ **跳过硬依赖 GCP 的模块 3/5** |
| **分层规范与命名** | `Smars-Bin-Hu/EComDWH...` ⭐173 | 四份规范文件 → 抄成《日志数仓分层与命名规范》 |
| **维度建模（星型/雪花）** | `DataWithBaraa` `scripts/gold/` + `data_models.drawio` | 事实表/维表划分与建表写法；**照画一张日志星型模型** |
| **数据质量校验报告** | **`abeltavares/batch-data-pipeline` ⭐90** | **只抄 `soda/checks.yml` 那 20 条检查**（行数上下限、schema 必填、4 类缺失、负数量/负金额/零数量、总额=数量×单价、去重、2 小时新鲜度、枚举值、avg/max 区间、ID 范围）+ `src/generators/sales_generator.py` 的「**故意注入 20% 脏数据再验证拦截**」思路。⚠️ 13 容器/8GB 偏重，且用 DuckDB 不是 Spark |
| **业务指标 SQL（漏斗/留存/复购）** | `lhq-123/Spark-Flink-DataWarehouse` ⭐46 | 只读 `5_ads/*.sql` 与 `3_dwd/ddl/fact_ddl.sql` |
| **Hive vs Spark SQL 实证** | `big-data-europe/docker-hive` ⭐1081 | 同一份 DDL 在两个引擎上各跑一遍，对比 `EXPLAIN` 与耗时 → **面经原题的直接弹药** |
| **监控（加分）** | `Smars-Bin-Hu` `src/infra/monitoring-config/` | Prometheus + Grafana + AlertManager 配置与启停脚本；**最简版用「执行日志 + 失败退出码」即可** |
| **WSL2 CRLF 坑** | `Smars-Bin-Hu` `docs/doc/error-handling/` | `.sh` 必须 LF：配好 `.gitattributes` 与 `git config core.autocrlf` |

**数据源**：NASA HTTP 访问日志（`ita.ee.lbl.gov/html/contrib/NASA-HTTP.html`，**已核验 HTTP 200**，两个月日志约 30–50MB，需先 gunzip）。
> ⚠️ **重要提醒**：**GitHub 上不存在「NASA 日志数仓」这类现成参考项目**。按 `nasa http log` 检索命中的仓库全是 **0–1 star 的个人小作业** —— **别指望找到现成的，您的项目 3 是原创，这反而是优势**。

**一条现实的技术路线（8～9 周能做完成、且面试讲得清）**
```
NASA HTTP 日志（公开镜像下载 30–50MB，先 gunzip）
  → ODS：Shell 采集 + PySpark 解析 → Parquet 按 dt 分区落本地磁盘
  → DWD：Spark SQL 清洗/规范化/去重（明细事实表 + 时间/URL/状态码/UA 维表）
  → DWS：Spark SQL 按小时/会话/URL 聚合宽表
  → ADS：PV/UV/独立IP/错误率/流量TopN/时段分布 等指标表 → MySQL 单容器
  → 质量校验：Python/SQL 校验脚本 → 输出 Markdown/HTML 报告（照抄那 20 条检查）
  → 调度：Makefile + cron（0 2 * * *），入口唯一 bash run_pipeline.sh
```
- **引擎**：`Spark local[*]`（或 `spark-submit --master spark://spark-master:7077` 打到 4.6 那个 standalone 集群，显得更像集群）——**不要装真 Hadoop/YARN 集群**。
- **硬件底线**：Docker 分 8–12GB 内存。
- **❌ 应当砍掉的炫技组件**（对神州 JD 是负收益）：Flink/Kafka 实时链路（JD 是离线 ETL，历史日志上流式纯属自找麻烦）；Doris/Paimon/Hudi/Iceberg/Kylin/ClickHouse/Presto/Dinky/SeaTunnel（单机跑不动，**简历堆名字会被追问穿帮**）；CDH/Hadoop HA 多节点/YARN 调优；K8s/Terraform；Databricks/BigQuery/GCP/Azure（引入账号、额度、网络三重不确定性）。
- **一句话**：`run_pipeline.sh` 里出现的是 **Shell、Python、Spark SQL、MySQL、cron** 这五样 —— 正对神州信息那份 JD。

### 6.4 BI 看板产出（三个项目通用）

> **先说一个重要判断**：**Power BI 方向没有合格的「可复现代码仓库」**。微软官方 `microsoft/powerbi-desktop-samples`（⭐2116、push 2026-09、MIT）里**几乎全是 .pbix 二进制 + JSON Schema**，GitHub 上无法 diff、面试官看不到您的建模逻辑。凡涉及「BI 看板」的产出物，**优先走 ECharts / Python 路线**——代码能进 Git 仓库、面试官能看懂、可复现。

| 仓库 | ⭐ | 最后推送 | 许可 | 定位与用法 |
| --- | --- | --- | --- | --- |
| **`pyecharts/pyecharts`** | 15,773 | 2026-08 | **MIT** ✓ | **最省力引擎（1～2 天出图）**：`pip install pyecharts` → pandas `groupby` 聚合 → `Bar()`（月度趋势）+ `Pie()`（品类占比）+ `Map()`（地域分布）→ `Page()` 拼成一页 → `.render("dashboard.html")` → **一个能双击打开的交互式 HTML 看板，≥3 张 ECharts 图** |
| `pyecharts/pyecharts-gallery` | 1440 | 2026-02 | **MIT** ✓ | **图表配方书（半天～1 天）**：要什么图就去对应目录抄 `xxx_base.py`，把 `Faker.choose()` 换成您的聚合结果。**3 天内凑齐 ≥3 张图最快的路径** |
| `jackchen0120/vueDataV` | 2178 | 2024-03 | **MIT** ✓ | **本批许可最干净的真前端项目**：Vue2 + ECharts，含 **26+ 个封装组件**（3D 柱、柱饼联动、水球图、司南排名…）。⚠️ **`node-sass ^4.13.1` 在 Node 16+ 基本装不上**，README 自己写「建议 node v12」→ 要么用 Node 12/14，要么把 `node-sass` 换成 `sass` |
| `evidence-dev/evidence` | 6947 | 2026-09 | MIT | **代码化 BI（BI-as-code）**：SQL + Markdown 写报表，一条命令起本地站点并**发布静态页面**→ **作品集链接可直接给面试官**。`evidence init` → 连 DuckDB（正好接 `jaffle_shop_duckdb`）→ 写 3 页（留存对比 + CI 误差线 / 漏斗 / 实验结论）→ 发布 |
| `dataease/dataease` | 24,444 | 2026-09 | 开源 | **FineBI 的国产开源对标**（中文界面、拖拉拽仪表板，Docker 一键部署）。**网易 JD 写「了解 BI 工具」→ 用它做 3 张图 + 录 1 分钟操作视频，比空口说「我会 FineBI」有说服力得多** |
| `apache/superset` ⭐74822 ｜ `metabase/metabase` ⭐49324 | — | 2026-09 | 开源 | 两大开源 BI 平台。**只选一个**（建议 Metabase 上手、Superset 写在简历上更「数据平台」）→ `docker compose up` → 接您的库 → SQL 建「留存对比/漏斗/分群」三张图 |
| `apache/echarts` | 67,348 | 2026-09 | Apache-2.0 | 图表引擎本体 + 官方示例库。找 boxplot / 误差线 / 漏斗图 → 画「带 CI 误差线的组间对比图」→ 拼成单页 HTML 大屏（可作简历附件） |
| ❌ `iGaoWei/BigDataView` | 5332 | 2025-10 | **无** | **无许可证 + README 自述素材为网络收集** → 只能当「看板外壳」，**绝不能声称原创**（仓库 901MB，含公众号引流） |
| ❌ `yyhsong/iDataV` | 5702 | **2021-07** | **无** | 停更 5 年 2 个月 + ECharts 3.8.5 老版本 + 约 1/4 内容是**商业大屏平台截图无代码** |
| ❌ `DataV-Team/DataV` | 9709 | 2024-06 | MIT | 是 **Vue2 组件库（零件）不是看板**，无布局无数据；OSSF Scorecard 判定近 90 天 0 提交 0 issue |

**推荐组合**：**`pyecharts` 出图 + `pyecharts-gallery` 抄配方 + `evidence` 发布链接 + `dataease` 录操作视频** —— 四件套覆盖「会出图、能展示、可复现、会商业 BI」四个层次，全部免费。

---

## 七、14 天起步复现行动清单（2026-09-17 晚 ~ 09-30）

> 对齐《入职计划 v2》的「48 小时起步动作」，并把 GitHub 复现节奏嵌进去。**每天 2-3 小时学习 + 30-60 分钟娱乐回血不变**（娱乐时间是硬红线）。

### 今天（09-17 晚，约 1.5 小时）
| # | 动作 | 产出 | 耗时 |
| --- | --- | --- | --- |
| 1 | 确认环境（本机已具备 **git 2.55 / Python 3.12 / Node 24**） | 环境确认 | 5 min |
| 2 | 建 GitHub 学习仓库 `data-career-roadmap`，README 放本清单的「映射总表」+ 打卡文件 `log/2026-09.md`，完成首次 commit | 仓库链接 | 30 min |
| 3 | 打开 **`sqlmother.yupi.icu`**，闯前 5 关（零安装、即时反馈） | 手感 + 截图 | 40 min |
| 4 | clone `datawhalechina/wonderful-sql`（慢就用 Gitee 镜像） | 本地中文教程 | 15 min |

### 24 小时内（09-18）
| # | 动作 | 产出 |
| --- | --- | --- |
| 5 | 装 **MySQL 8.0** + 客户端（**Navicat Premium Lite 已免费**，或 DBeaver）+ **Cursor**；跑通 `SELECT 1` | 本地 MySQL 可用 |
| 6 | 装 **Docker Desktop**（后面 `sql-tutorial`、`pagila`、`docker-hive` 都要用） | Docker 可用 |
| 7 | `wonderful-sql` ch00 环境搭建 + ch01 初识数据库 | 打卡 commit |

### 48 小时内（09-19）
| # | 动作 | 产出 |
| --- | --- | --- |
| 8 | `wonderful-sql` ch02 基础查询与排序；执行 `mysql < materials/create_table_sql/shop.sql` 与 `world.sql` | 两个练习库建好 |
| 9 | SQL 母网闯到 20 关 | 截图入 `log/2026-09.md` |
| 10 | 光伏项目 STAR 简历段 v0.1（数字现成：2000 万→1400 万，-30%）存 `resume/project-v0.1.md` | 简历初稿 |

### 第 1 周收尾（09-20 ~ 09-23）
| # | 动作 | 产出 |
| --- | --- | --- |
| 11 | `wonderful-sql` ch03（视图/子查询/函数/谓词/**CASE**）—— **CASE 是条件聚合的地基，务必手敲** | ch03 习题完成 |
| 12 | `wonderful-sql` ch04（集合运算 + JOIN） | ch04 习题完成 |
| 13 | clone `civilian7/sql-tutorial`，用 Docker 起 MySQL 容器，生成 `--size small`（**75 万行**） | 30 表数据库可用 |
| 14 | 读 `sql-tutorial` 表结构，写出「订单 + 订单明细 + 商品」三表 JOIN 自测题 5 道并作答 | 5 道自测题 |
| 15 | **每完成一项即 commit 一次**（目标：14 天连续绿色格子） | 周复盘 |

### 第 2 周（09-24 ~ 09-30）
| # | 动作 | 产出 |
| --- | --- | --- |
| 16 | `sql-tutorial` beginner 00–07（英文教程起点） | beginner 题集前半 |
| 17 | `wonderful-sql` **ch05 SQL 高级处理**（窗口函数 / GROUPING / 存储过程） | ch05 习题完成 |
| 18 | 牛客 SQL 题库累计 ≥20 题 | 正确率记录入打卡 |
| 19 | 运行 `python -m src.verify.verify` 跑通官方校验 | 校验通过 |
| 20 | 建「AI 辅助写 SQL」留档（每次记录：**我让 AI 做了什么 + 我校验了什么**），目标 ≥3 条 | `docs/ai-assisted-sql.md` |

### 14 天里程碑自查（09-30）
- [ ] `data-career-roadmap` 仓库 ≥10 次 commit、14 天中 ≥12 天有绿色格子
- [ ] 本地 MySQL 有 2 个可用练习库（shop/world + `sql-tutorial` 的 30 表 75 万行）
- [ ] `wonderful-sql` ch00–ch05 完成，ch06 至少手写 3 题
- [ ] 牛客 SQL ≥20 题、SQL 母网 ≥20 关
- [ ] 能不看文档手写「GROUP BY + CASE WHEN 条件聚合」与「ROW_NUMBER() 分组取 Top1」
- [ ] 「AI 辅助写 SQL」留档 ≥3 条（站 4 大模型实例的源头）
- [ ] **娱乐回血时间一天都没被砍**（硬红线）

---

## 八、避坑清单与质量说明

### 8.1 明确不要用的仓库（本次核验中淘汰）

| 仓库 | 实测 ⭐ | 实测最后推送 | 淘汰原因 |
| --- | --- | --- | --- |
| `DataWithDanny/sql-masterclass` | 2334 | 2023-02 | 停更 3 年半 + 数据不在仓库里 |
| `WebDevSimplified/Learn-SQL` | 1795 | — | 仓库仅 15KB，只有练习文本，不带数据库 |
| `NUKnightLab/sql-mysteries` | 2217 | — | 趣味推理小游戏，数据量太小 |
| `lerocha/chinook-database` | 2612 | — | 全库约 1.5 万行，只够第 1 周热身 |
| `yyhsong/iDataV` | 5702 | **2021-07** | 停更 5 年 2 个月 + ECharts 3.8.5 + 1/4 内容是商业平台截图 + 无许可证 |
| `iGaoWei/BigDataView` | 5332 | 2025-10 | **无许可证 + 素材网络收集** → 只能当外壳，**绝不能声称原创** |
| `datawhalechina/fantastic-matplotlib` | 528 | 2022-07 | 停更 4 年 2 个月 |
| `airscholar/e2e-data-engineering` | 361 | — | **不推荐复现**：全仓库仅 8 个文件、**零数仓分层、零质量校验**，且实测 3 个坑：`spark_stream.py` 硬编码 `localhost` 却无对应服务、`requirements.txt` 把 `pyspark` 注释掉却引入无关的 `spark==0.2.1`、**`create_table` 缺 `dob` 字段而 `INSERT` 里有 `dob`（新克隆首次写入大概率直接失败）** |
| `simbafl/DataWarehouse` | 650 | 2022-01 | 停更 4.6 年 |
| `oeljeklaus-you/UserActionAnalyzePlatform` | 1132 | 2022-11 | 停更 3.9 年 |
| `AlexIoannides/pyspark-example-project` | 2118 | 2023-01 | 停更 3.7 年 |
| `clklog/clklog` | 188 | 2026-09 | 国产开源埋点平台，但**漏斗分析与留存分析属 PRO 商业版**，社区版没有 |
| `CNSRE/ABTestingGateway`（新浪） | 2348 | 2018-10 | 停更 8 年 → **只看架构与分流策略，不要复现** |
| `AtmosphereMao/BigDataAnalysis`<br>`sengchih/Flink-DataWarehouse`<br>`zhengzebiaodashi/BigData-Notes` | — | — | **这三个仓库根本不存在**（已逐个反查：前者用户 34 个仓库中无此库；中者连用户都不存在；后者用户 0 个公开仓库）→ 若您在别处看到这三个名字，是记错了 owner/库名 |

### 8.2 三个必须知道的使用红线

1. **许可证**：`wonderful-sql`、`heibaiying/BigData-Notes`、`juicy-bigdata`、`lhq-123/Spark-Flink-DataWarehouse`、`iGaoWei/BigDataView`、`yyhsong/iDataV`、`datawhalechina/hands-on-data-analysis` **均无许可证**（或未声明）→ **只能学习参考，不能把内容/代码搬进自己的仓库**。
   **可安全复用（宽松许可）**：`pyecharts`（MIT）、`pyecharts-gallery`（MIT）、`jackchen0120/vueDataV`（MIT）、`evidence`（MIT）、`ali12hamdan/ab-test-cookie-cats`（见仓库 `LICENSE`）、`civilian7/sql-tutorial`（代码 MIT，**内容 CC BY-NC-SA 非商用**）、`MrSuiChuan/data-warehouse-learning`（Artistic-2.0）、`Smars-Bin-Hu/EComDWH...`（MIT）、`abeltavares/batch-data-pipeline`（MIT）。
2. **fork 陷阱**：`data-warehouse-learning` 在 GitHub 上有**多个 0 star 的同名 fork**。认准 ⭐1243 的 `MrSuiChuan/data-warehouse-learning`（或上游 `Mrkuhuo/data-warehouse-learning`）。
3. **「课程引流」型仓库**（代码免费可用，但 README 下半是卖课闭环）：`DataWithBaraa/sql-data-warehouse-project`、`josephmachado/efficient_data_processing_spark`（配 podia.com 优惠码）、`DataTalksClub/data-engineering-zoomcamp`（免费无付费墙，但有注册/Slack/YouTube 引流，内容与赞助商产品重合）。**当纯代码仓库用即可，别被引流带走。**

### 8.3 核验方法说明（可复查）

- **星标 / 最后推送**：GitHub REST API、`ungh.cc` 实时代理、`img.shields.io` 徽章**三源交叉**；凡快照源与实时源不一致处，一律以实时源为准并标注过时值。
- **内容实质**：逐个抓取 README、`package.json`、`docker-compose.yml`、**全量文件树**（`data.jsdelivr.com` / `ungh.cc/files`）、关键源码与 Makefile 正文，确认「是真代码还是只有笔记」——本清单中所有「可跑 / 不可跑」的判断**均基于实测文件，不采信 README 自述**。
- **外部资源可达性实测（HTTP 200）**：Cookie Cats 数据集、Solar Power Generation、UCI 家庭用电（**静态 zip 可直下，20,640,916 字节**）、Steam Store Games、NASA HTTP 日志（ita.ee.lbl.gov）、SQL 母网站点。
- **已反查纠正 3 个不存在的仓库**（见 8.1 末行）。
- **纠正了一处常见误传**：`MrSuiChuan/data-warehouse-learning` 常被当作「可跑的数仓项目」，实测是**文档+截图型仓库**（根目录仅 4 项、34MB 几乎全是图片）；`DataV-Team/DataV` 常被说「停更超 3 年」，实测停更 2 年 3 个月，**排除它的真实理由是「它是组件库不是看板」**。

### 8.4 已知未能核验项（诚实标注）

- `microsoft/powerbi-desktop-samples`：⭐2116、push 2026-09、MIT 已核验，但 `Sample Reports/` 内**具体 .pbix 文件名清单未能核验**（GitHub API 限流 + 仓库超 jsDelivr 50MB 上限）。
- `big-data-europe/docker-hive`：⭐1081 来自 shields.io + ungh.cc 交叉（API 额度耗尽后未能直读），**存在少量滞后可能**；README 里 `kv1.txt` 是否真在镜像内未核验。
- `lhq-123/Spark-Flink-DataWarehouse`：因仓库超 50MB，`data.jsdelivr.com` 返回 403，文件树改用 `ungh.cc/files` 获取（已交叉确认）；`pom.xml` 抓取 404（根目录本就无 Maven 构建）。
- `cluster-apps-on-docker/spark-standalone-cluster-on-docker`：根目录 `docker-compose.yml` 的 raw 抓取 404，与 jsDelivr 清单不一致 → 已只引用 README 明确给出的 `assets/docker-compose.yml` 路径。
- `datawhalechina/hands-on-data-analysis`：已确认「课程 + 答案两套结构」与主 notebook 可运行，**未逐页打开每个答案文件**。
- A/B 方向多个仓库（`ThinkStats2`/`ThinkBayes2`/`lifelines`/`dataease`/`superset`/`metabase`/`echarts`/`data-formulator`）为**元数据已核验、README 未逐行读取**，其 内容描述基于公开目录或产品定位。
