# Personal Distillation Coach

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

## 3. 如何使用

### 3.1 通用模式（推荐默认）

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

### 3.2 个性模式（仅明确要求时）

当你要调用个人参数时，在请求里明确写出：

```text
/personal-distillation-coach 使用个性版：帮我写秋招 30 秒自我介绍
```

个性模式输出结构：
1. 数字生命判断
2. 场景化结果
3. 一致性检查
4. 进化建议

## 4. 建模最小输入（通用）

若信息不足，可先补这 5 项：

1. 用于什么场景（求职/创作/复盘/决策）
2. 最看重哪三项（价值判断/审美偏好/决策方式/表达风格）
3. 输出风格偏好（理性/温和/锋利/克制）
4. 灵魂表达与职业表达比例（如 7:3）
5. 是否需要匿名化处理（是/否）

## 5. 隐私与脱敏

- 默认避免真实公司名称等可识别信息。
- 详细规则见：`.cursor/skills/personal-distillation-coach/privacy.md`

## 6. 持续迭代建议

- 每周更新一次认知变化，记录到 `memory-ledger.md`。
- 新增参考文章放入 `references/` 对应分类目录。
- 重要稳定信息同步沉淀到 `reference.md`。
