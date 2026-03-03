# 游戏分析与逆向拆解专家 Skill

[![Oh My OpenCode Skill](https://img.shields.io/badge/OpenCode-Skill-blue.svg)](https://github.com/code-yeongyu/oh-my-opencode)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

基于 **Oh My OpenCode (OMO)** 框架多智能体能力的游戏分析 Skill。它能够对任何给定的游戏进行较全面的拆解，适用于快速对一款游戏建立认知。

## 🌟 核心特性 (Features)

本 Skill 突破了单体大模型的 “幻觉” 与 “惰性” 限制，采用了 Map-Reduce 并行架构：

1. **五大视角并发 (Map 阶段)**：同时唤起 5 个专职 Subagents（制作人、主策、主美、运营总监、战略分析师），各自携带长达 200+ 行的专业级验收 SOP 去全网检索信息。
2. **高价值信源过滤**：内置防幻觉（Anti-Hallucination）降级策略，强制要求附带 Execution Log（执行日志）。
3. **顶层调和审查 (Reduce 阶段)**：强制唤起拥有最高推理能力的 `Oracle` (主编) 智能体，审查 5 份原稿的逻辑冲突，并出具投研级《多维度评估总结》。
4. **双文件输出流**：最终生成一份原汁原味的深度报告正文，以及一份用于追溯和优化 SOP 的工程日志。

## 📦 目录结构 (Structure)

```text
game-teardown-expert/
├── SKILL.md                          # 技能入口、并发任务调度逻辑与输出模板
├── README.md                         # 本说明文件
└── references/
    └── teardown_sop_framework.md     # 核心知识库：200+行的五大视角分析 SOP
```

## 🚀 安装指南 (Installation)

### 前置要求
本 Skill 依赖于 [Oh My OpenCode](https://github.com/code-yeongyu/oh-my-opencode) 提供的 `task` 并发调度能力。请确保你已安装并配置好该环境。

### 全局安装 (Global Install)
将本项目克隆或下载后，将整个 `game-teardown-expert` 文件夹放入你的全局 Agent 技能目录中：

- **Windows**: `C:\Users\<YourUsername>\.opencode\skills\` 或 `C:\Users\<YourUsername>\.agents\skills\`
- **Mac/Linux**: `~/.opencode/skills/` 或 `~/.agents/skills/`

## 💡 如何使用 (Usage)

重启你的 Agent 客户端，开启一个新的 Session，然后输入以下指令：

> "请使用 `skill(name='game-teardown-expert')` 对《xxx》进行分析。"

系统将自动触发环境自检，随后你将看到后台并发启动 5 个任务，并在 15 分钟内交付报告。
