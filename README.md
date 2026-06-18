# 多视角思维顾问 · Multi-Perspective Advisor

> **一句话：** 复杂决策的秒级专家团。说一个问题，14 个不同领域的大师同时回答你。

[![Skill](https://img.shields.io/badge/Skill-Multi--Perspective-blue)](./SKILL.md)
[![Version](https://img.shields.io/badge/version-1.1.0-green)](./CHANGELOG.md)
[![Perspectives](https://img.shields.io/badge/perspectives-14-orange)](./SKILL.md)
[![License](https://img.shields.io/badge/license-MIT-yellow)](./LICENSE)

---

## 你什么时候需要它？

- 面对一个复杂决策（投资、创业、职业选择、技术选型）不知道怎么权衡
- 感觉"好像有多个角度，但说不清楚"
- 想让一群不同背景的大师同时帮你分析问题，而不是只看到一个视角
- 用户明确要求"换个角度想想""有没有不同视角"

## 它会交付什么？

- 一个按**主题分组**的综合分析报告（不是 14 份独立报告，而是共识与分歧的归并）
- 明确标注哪些观点是共识，哪些是分歧
- 具体可执行的行动建议（不停留在抽象讨论）
- 2000-4000 字的完整分析

```
你: "帮我多视角分析一下：我该不该现在买入英伟达股票？"
→ 4-8 个视角同时分析 → 按主题归并 → 综合报告
```

## 安装方式

选择最适合你的平台：

### 方式 1：WorkBuddy（推荐 · 当前环境）

```bash
# Skill 已安装在 ~/.workbuddy/skills/multi-perspective-advisor/
# 直接在任何对话中触发即可
```

### 方式 2：Claude Code / Codex

将 `multi-perspective-advisor/` 整个文件夹拷贝到你的 Agent skill 目录：

**Claude Code:**
```bash
# macOS/Linux
cp -r multi-perspective-advisor/ ~/.claude/skills/

# Windows (PowerShell)
Copy-Item -Recurse multi-perspective-advisor\ $env:USERPROFILE\.claude\skills\
```

**Codex:**
```bash
# 将目录放到 Codex 的 skill 搜索路径下
cp -r multi-perspective-advisor/ /path/to/codex/skills/
```

### 方式 3：OpenClaw

```bash
# 方法 A：通过 ClawHub 安装
clawhub install <your-username>/multi-perspective-advisor

# 方法 B：手动安装
mkdir -p ~/.openclaw/skills/
cp -r multi-perspective-advisor/* ~/.openclaw/skills/multi-perspective-advisor/
```

### 方式 4：GitHub 仓库 + 手动安装

```bash
# 1. Clone 仓库
git clone https://github.com/<your-username>/multi-perspective-advisor.git

# 2. 拷贝到你的 Agent skill 目录
cp -r multi-perspective-advisor/ ~/.your-agent/skills/

# 3. 或者通过 npx 安装到 skills.sh registry
npx skillsadd <your-username>/multi-perspective-advisor
```

### 前置条件：安装 Perspective 技能

此 Skill 依赖 14 个 Perspective 技能中的至少 1 个（推荐 4+ 个）：

```bash
# 安装推荐（至少 4 个不同领域的）
cp -r ~/.workbuddy/skills/nuwa-skill/examples/elon-musk-perspective/ ~/.your-agent/skills/
cp -r ~/.workbuddy/skills/nuwa-skill/examples/munger-perspective/ ~/.your-agent/skills/
cp -r ~/.workbuddy/skills/nuwa-skill/examples/taleb-perspective/ ~/.your-agent/skills/
cp -r ~/.workbuddy/skills/nuwa-skill/examples/zhang-yiming-perspective/ ~/.your-agent/skills/
```

> **提示：** Perspective 技能越多，分析维度越丰富。但至少安装 1 个才能让多视角分析生效。

## 快速开始

**Step 1:** 确保安装了至少 1 个 Perspective 技能（推荐 4+ 个）

**Step 2:** 在你的 Agent 中直接说：

> "帮我多视角分析一下：[你的问题]"

**Step 3:** 查看综合分析报告

**Step 4:** （可选）追问某个维度的细节，或要求换一个视角组合重新分析

## 触发方式

- "帮我多视角分析一下：[你的问题]"
- "用 4 个视角判断：[某事]"
- "换个角度想想[某事]"
- "你有没有不同视角？"
- "[某事] 应该怎么决策？"
- "从多个维度分析一下[某事]"
- "这个问题我该怎么看？"
- "用大师们的智慧帮我分析一下[某事]"

## 示例

假设用户问："我该不该现在买入英伟达股票？"

**核心结论：** 多数视角认为短期估值偏高存在回调风险，但长期 AI 基础设施需求远未被满足；行动建议是分批建仓而非一次性投入。

**维度一：估值与风险**
- **共识**：马斯克、塔勒布、孙宇晨一致认为当前价格已反映较多乐观预期
- **分歧**：
  - **马斯克**：硬件供应链的竞争壁垒比终端芯片更高
  - **塔勒布**：尾部风险不对称，建议杠铃策略
  - **孙宇晨**：市场情绪已接近狂热区间

## 它和同类有什么不同？

| 对比维度 | 多视角思维顾问 | 一般多视角分析 prompt |
|---|---|---|
| 视角数量 | 14 个专业级 Perspective 技能 | 通常 0-2 个 |
| 输出方式 | 按主题归并共识与分歧 | 按人罗列"谁说啥" |
| 视角选择 | 智能诊断问题类型 + 跨领域强制要求 | 随机或固定组合 |
| 视角激活 | 自动探测 + 降级 fallback | 硬编码或手动指定 |
| 分析深度 | 每个视角有自己的心智模型和启发式 | 通常是通用提示语 |

## 视角地图（14 位大师）

| 类别 | 视角 | 擅长 |
|------|------|------|
| 科学/认知 | 费曼 | 教学、概念拆解 |
| 科学/认知 | Karpathy | AI/ML/工程 |
| 科学/认知 | Ilya Sutskever | AI安全/基础研究 |
| 科学/认知 | 芒格 | 跨学科投资思维 |
| 商业/战略 | 马斯克 | 成本/物理极限 |
| 商业/战略 | 乔布斯 | 产品设计/体验 |
| 商业/战略 | 张一鸣 | 系统效率/信息匹配 |
| 商业/战略 | Paul Graham | 创业/产品市场 |
| 商业/战略 | Naval | 财富杠杆/复利 |
| 创意/内容 | MrBeast | 注意力/内容节奏 |
| 创意/内容 | 孙宇晨 | 投机套利/情绪博弈 |
| 风险/哲学 | 塔勒布 | 尾部风险/反脆弱 |
| 风险/哲学 | 特朗普 | 权力博弈/谈判 |
| 实战/方法 | 张学峰 | 教育规划/职业选择 |

## 安全边界

- **不会做的事：** 不替代你的决策，只提供多角度分析
- **不会泄露：** 不存储你的问题或个人信息
- **不确定的坦诚：** 如果某个视角在当前问题上帮不上忙，会直接说
- **事实查询拒绝：** fact-based 问题不会用多视角分析器处理

## 兼容平台

此 Skill 是纯提示语文档，不依赖任何特定 Agent runtime：

- WorkBuddy（Skill 工具）
- Claude Code
- Codex
- OpenCode
- OpenClaw
- Hermes
- 任何支持 `.md` 格式 Skill 定义的 Agent 平台

## 文件结构

```
multi-perspective-advisor/
├── SKILL.md          # Skill 定义（执行规则）
├── README.md         # 你正在看的文件
├── DESIGN.md         # 架构设计与演进路线
├── CHANGELOG.md      # 版本变更记录
└── LICENSE
```

## 版本

- **当前版本**：v1.1.0
- **发布日期**：2026-06-18
- **变更日志**：[CHANGELOG.md](./CHANGELOG.md)

## 许可

MIT — 随便用，随便改，随便用它帮你多角度思考。
