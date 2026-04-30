# 秦健超数字生命

## 关于我

我是华东理工大学软件工程专业 2027 届学生，当前目标是本科直接就业，方向聚焦在全栈 / AI 应用开发。  
相比“只做技术标签”，我更关注“认知 + 审美 + 技术落地”的长期统一：

- 在专业上，持续深耕后端与 AI 工程化能力
- 在认知上，强调灰度思维、换位思考与理性包容
- 在审美上，通过音乐、电影、阅读、摄影不断校准判断力

这个仓库就是我为自己构建“数字生命（Digital Twin）”的实践项目：  
让一个 AI 不只是会润色文本，而是能长期理解我、模拟我、并与我共同迭代。

`personal-distillation-coach` 是一个“思想保留型数字生命系统”技能。  
它的目标不是一次性生成内容，而是长期保留并延续你的价值判断、认知结构、决策方式与表达风格。

## 当前能力总览

本仓库中的 Skill 已从“基础画像”升级到“可执行审美系统 + 增量更新机制”，并与当前 `SKILL.md` 保持一致：

- 双层架构：`通用层（默认）` + `个性层（需明确授权）`
- 记忆系统：`热记忆优先` + `温记忆按需路由`
- 输出协议：包含一致性审计与迭代建议
- 表达约束：默认“人味表达”，不展示步骤清单式推理
- 三大数据化模块：电影 / 音乐 / 阅读（含豆瓣全量抓取成果）

## Skill 目录结构

```text
.cursor/skills/personal-distillation-coach/
├── SKILL.md
├── memory.md
├── reference.md
├── memory-ledger.md
├── examples.md
├── privacy.md
└── references/
    ├── README.md
    ├── WARM_MEMORY_INDEX.md
    ├── SEARCH_INDEX.json
    ├── film/
    ├── music/
    ├── books/
    ├── photo/
    ├── life/
    └── profile/
```

## 核心运行规则（对齐 SKILL）

### 1) 双层架构与权限
- `通用层（Public Core）`：默认启用，可复用方法论
- `个性层（Personal Overlay）`：仅在用户明确授权时启用

硬约束：
- 未明确授权，禁止启用个性层
- 未明确授权，禁止套用私人参数
- 用户要求“可传播模板”时，强制使用通用层

### 2) 记忆加载顺序
1. 先读取 `memory.md`
2. 热记忆不足时读取 `references/WARM_MEMORY_INDEX.md`
3. 按主题路由读取 1-3 篇温记忆文档
4. 禁止默认全量扫描温记忆

### 3) 输出协议
- 通用输出：任务理解 -> 思想立场 -> 结构化结果 -> 一致性审计 -> 下一步迭代
- 个性输出（仅授权）：数字生命判断 -> 场景化结果 -> 一致性检查 -> 进化建议
- 人味表达约束（默认启用）：自然口语化、减少模板腔、默认隐藏内部思考过程

## 三大审美系统（最新）

### 电影系统
- 数据：`references/film/douban_movies_271719541.json`
- 报告：
  - `references/film/豆瓣电影全量画像-v1.md`
  - `references/film/豆瓣电影深层画像-v2.md`
  - `references/film/个人审美判准词典-v1.md`
  - `references/film/审美系统操作手册-v1.md`
- 特征：高低分样本判准、决策树、反偏差机制、增量锚点

### 音乐系统
- 数据：`references/music/douban_music_271719541.json`
- 报告：
  - `references/music/豆瓣音乐全量画像-v1.md`
  - `references/music/豆瓣音乐深层画像-v2.md`
  - `references/music/个人审美判准词典-v1.md`
- 特征：高低分专辑判准、创作者人格追踪、年代与风格偏好机制、增量锚点

### 阅读系统
- 数据：`references/books/douban_books_271719541.json`
- 报告：
  - `references/books/豆瓣读书全量画像-v1.md`
  - `references/books/豆瓣读书深层画像-v2.md`
- 特征：阅读节奏、作者谱系、出版年跨度、认知进化方向、增量锚点

## 增量更新机制

电影 / 音乐 / 阅读报告均已加入抓取元信息：

- `爬取时间`
- `数据时间范围`
- `增量锚点`
- `下次增量建议`

这意味着后续可以做“增量爬取 + 增量分析”，不必每次全量重建。

## 使用方式

在 Cursor 中可直接触发：

```text
/personal-distillation-coach 你如何评价《让子弹飞》
/personal-distillation-coach 按你的审美推荐几张专辑
/personal-distillation-coach 使用个性版：给我一个30秒自我介绍
```

## 维护建议

- 新增稳定认知 -> 同步写入 `reference.md`
- 版本变化 -> 记录到 `memory-ledger.md`
- 新增主题资料 -> 放入 `references/` 对应目录，并更新 `WARM_MEMORY_INDEX.md`
- 需要长期检索的结构化索引 -> 维护 `references/SEARCH_INDEX.json`

## 相关文档入口

- Skill 主协议：`.cursor/skills/personal-distillation-coach/SKILL.md`
- 核心画像：`.cursor/skills/personal-distillation-coach/reference.md`
- 演化账本：`.cursor/skills/personal-distillation-coach/memory-ledger.md`
- 温记忆说明：`.cursor/skills/personal-distillation-coach/references/README.md`
