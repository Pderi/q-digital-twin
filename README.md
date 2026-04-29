# 秦健超数字生命

## 0. 关于我

我是华东理工大学软件工程专业 2027 届学生，当前目标是本科直接就业，方向聚焦在全栈 / AI 应用开发。  
相比“只做技术标签”，我更关注“认知 + 审美 + 技术落地”的长期统一：

- 在专业上，持续深耕后端与 AI 工程化能力
- 在认知上，强调灰度思维、换位思考与理性包容
- 在审美上，通过音乐、电影、阅读、摄影不断校准判断力

这个仓库就是我为自己构建“数字生命（Digital Twin）”的实践项目：  
让一个 AI 不只是会润色文本，而是能长期理解我、模拟我、并与我共同迭代。

---

一个用于构建“数字生命（Digital Twin）”的 Cursor Skill。  
目标不是一次性润色文案，而是沉淀一个可长期迭代的人格-决策-表达系统。

## 1. Skill 简介

`personal-distillation-coach` 提供两层能力：

- `通用层（Public Core）`：任何人可复用的数字生命蒸馏方法。
- `个性层（Personal Overlay）`：在用户明确要求时，叠加个人参数进行定制输出。

默认规则（已写死）：  
**默认只走通用层**，只有用户明确说“使用个性版/Personal Overlay”才切换个性层。

## 2. 项目结构

```text
.cursor/skills/personal-distillation-coach/
├── SKILL.md          # 技能主协议（核心规则）
├── reference.md      # 画像与认知参考资料
├── examples.md       # 示例输入输出
├── privacy.md        # 脱敏与匿名化规则
├── memory-ledger.md  # 数字生命版本演化记录
└── references/       # 额外参考文档目录
    └── README.md
```

## 3. 保姆级安装教程（从 0 开始）

### 3.1 你最终要放到哪里

本项目的技能目录是：

`./.cursor/skills/personal-distillation-coach/`

如果你要在**另一个项目**复用，直接把这整个目录复制过去，目标路径保持一致：

`你的项目根目录/.cursor/skills/personal-distillation-coach/`

> 关键点：一定是 `.cursor/skills/技能名/` 这层级，不要少一层或多一层。

### 3.2 在 Cursor 里安装（本地项目）

1. 打开你的项目根目录  
2. 确认有 `.cursor/skills/` 目录（没有就新建）  
3. 复制 `personal-distillation-coach` 文件夹到 `.cursor/skills/` 下  
4. 重启当前 Cursor 对话，或新开一个会话  
5. 在聊天里输入 `/personal-distillation-coach` 测试是否可调用

### 3.3 安装后自检（建议必做）

至少做这 3 条：

1. 目录检查：  
   `你的项目/.cursor/skills/personal-distillation-coach/SKILL.md` 必须存在  
2. 触发检查：  
   在对话输入 `/personal-distillation-coach 介绍一下你能做什么`  
3. 规则检查：  
   不加“个性版”时，输出应走通用结构（任务理解 -> 结构化结果 -> 质量检查 -> 下一步动作）

## 4. 如何使用（Cursor 内）

### 4.1 通用模式（推荐默认）

适合分享给任何人，结构统一、可复用。

触发示例：

```text
/personal-distillation-coach 帮我做一个用于求职的数字生命版本
/personal-distillation-coach 评价一下《让子弹飞》
```

默认输出结构：
1. 任务理解
2. 结构化结果
3. 质量检查
4. 下一步动作

### 4.2 个性模式（仅明确要求时）

当你要调用个人参数时，在请求里明确写出：

```text
/personal-distillation-coach 使用个性版：帮我写秋招 30 秒自我介绍
```

个性模式输出结构：
1. 数字生命判断
2. 场景化结果
3. 一致性检查
4. 进化建议

## 5. 在其他 Agent 中怎么用（含 OpenClaw）

核心原则：**把这个 Skill 当“提示词协议包 + 资料库”使用**。

### 5.1 通用迁移方法（任何 Agent 都适用）

1. 把以下文件作为上下文提供给目标 Agent：  
   - `SKILL.md`（主协议）  
   - `reference.md`（画像参考）  
   - `privacy.md`（脱敏规则）  
   - `examples.md`（示例）  
2. 在你的系统提示或首条消息中声明：  
   - 默认走通用层  
   - 仅在你明确说“个性版”才启用个性层  
3. 发出任务时尽量用固定前缀：  
   - `使用 personal-distillation-coach（通用层）处理：...`

### 5.2 OpenClaw 使用方式（先检测，再决定）

先做原生支持检测：

1. 确保项目里存在：  
   `你的项目/.cursor/skills/personal-distillation-coach/SKILL.md`
2. 在 OpenClaw 直接输入：  
   `/personal-distillation-coach 介绍一下你能做什么`
3. 判断结果：  
   - 若能按技能结构稳定回复 -> 说明支持原生 Skill，直接使用  
   - 若无法识别或无结构回复 -> 使用“手动注入协议”方案

如果需要手动注入协议，按下面做：

1. 将 `SKILL.md` 的核心规则粘贴到 OpenClaw 的系统指令  
2. 将 `reference.md`、`examples.md` 作为附件或上下文文本输入  
3. 明确加一条硬规则：  
   - “默认通用层；仅当我输入‘使用个性版’时启用个性层”

示例指令：

```text
你现在使用 personal-distillation-coach 协议回答。
默认通用层输出结构：任务理解 -> 结构化结果 -> 质量检查 -> 下一步动作。
只有当我明确说“使用个性版”时，才切到个性输出。
先处理这个任务：评价一下《让子弹飞》。
```

### 5.3 OpenClaw 常见踩坑

- 只贴了 `reference.md`，没贴 `SKILL.md` -> 会丢规则  
- 没声明默认通用层 -> 容易跑到个人化结构  
- 不提供 `privacy.md` -> 容易出现隐私信息泄漏风险  
- 一次塞太多资料 -> 上下文截断，建议按任务分批喂
- 没先做“原生支持检测”就假定可用 -> 容易误判能力边界

## 6. 建模最小输入（通用）

若信息不足，可先补这 5 项：

1. 用于什么场景（求职/创作/复盘/决策）
2. 最看重哪三项（价值判断/审美偏好/决策方式/表达风格）
3. 输出风格偏好（理性/温和/锋利/克制）
4. 灵魂表达与职业表达比例（如 7:3）
5. 是否需要匿名化处理（是/否）

## 7. 隐私与脱敏

- 默认避免真实公司名称等可识别信息。
- 详细规则见：`.cursor/skills/personal-distillation-coach/privacy.md`

## 8. 持续迭代建议

- 每周更新一次认知变化，记录到 `memory-ledger.md`。
- 新增参考文章放入 `references/` 对应分类目录。
- 重要稳定信息同步沉淀到 `reference.md`。

## 9. 一分钟快速上手（给第一次用的人）

1. 复制目录到：`.cursor/skills/personal-distillation-coach/`  
2. 新开对话，输入：  
   `/personal-distillation-coach 帮我构建一个用于求职的数字生命版本`  
3. 想要通用输出就直接提问；想要个性输出就在开头加：`使用个性版`  
4. 每周一句话更新认知，写进 `memory-ledger.md`，持续迭代即可。
