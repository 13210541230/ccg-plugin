# CCG Plugin for Claude Code

> CCG (Claude + Codex + Gemini) 多模型协作开发系统的 Claude Code 插件发行版。

## 安装

```bash
# 1. 添加 marketplace
/plugin marketplace add 13210541230/ccg-plugin

# 2. 安装插件
/plugin install ccg@ccg-plugin
```

## 更新

```bash
/plugin update ccg@ccg-plugin
```

## 包含内容

| 组件 | 数量 | 说明 |
|------|------|------|
| 命令 | 27 | `/ccg:workflow`, `/ccg:plan`, `/ccg:execute` 等 |
| 子智能体 | 4 | planner, init-architect, ui-ux-designer, get-current-datetime |
| 专家提示词 | 19 | Codex 6 + Gemini 7 + Claude 6 |
| 输出风格 | 5 | 多种角色风格 |
| 二进制 | 6 | codeagent-wrapper 全平台预编译 |

## 命令列表

### 开发工作流

| 命令 | 用途 |
|------|------|
| `/ccg:workflow` | 完整 6 阶段工作流 |
| `/ccg:plan` | 多模型协作规划 |
| `/ccg:execute` | 多模型协作执行 |
| `/ccg:frontend` | 前端专项（Gemini） |
| `/ccg:backend` | 后端专项（Codex） |
| `/ccg:feat` | 智能功能开发 |
| `/ccg:analyze` | 技术分析 |
| `/ccg:debug` | 问题诊断 + 修复 |
| `/ccg:optimize` | 性能优化 |
| `/ccg:test` | 测试生成 |
| `/ccg:review` | 代码审查 |
| `/ccg:manage` | 主 Agent 调度 |

### Git 工具

| 命令 | 用途 |
|------|------|
| `/ccg:commit` | 智能提交 |
| `/ccg:rollback` | 交互式回滚 |
| `/ccg:clean-branches` | 清理已合并分支 |
| `/ccg:worktree` | Worktree 管理 |

### OpenSpec 系列

| 命令 | 用途 |
|------|------|
| `/ccg:spec-init` | OpenSpec 初始化 |
| `/ccg:spec-research` | 需求研究 |
| `/ccg:spec-plan` | 零决策规划 |
| `/ccg:spec-impl` | 规范驱动实现 |
| `/ccg:spec-review` | 归档前审查 |

### Agent Teams 并行实施

| 命令 | 用途 |
|------|------|
| `/ccg:team-research` | 并行需求探索 |
| `/ccg:team-plan` | 并行计划拆分 |
| `/ccg:team-exec` | 并行实施 |
| `/ccg:team-review` | 双模型交叉审查 |

### 其他

| 命令 | 用途 |
|------|------|
| `/ccg:enhance` | Prompt 增强 |
| `/ccg:init` | 初始化项目 CLAUDE.md |

## 构建来源

本仓库由 [ccg-workflow](https://github.com/13210541230/ccg-workflow) 的 `build-plugin.mjs` 脚本自动生成。

### 更新流程

```bash
# 在 ccg-workflow 项目中
node scripts/build-plugin.mjs --verbose

# 同步到本仓库
cp -r dist/plugin/* ../ccg-plugin/
cp -r dist/plugin/.claude-plugin ../ccg-plugin/
cp dist/plugin/.mcp.json ../ccg-plugin/

# 提交推送
cd ../ccg-plugin
git add -A && git commit -m "chore: sync plugin v<version>" && git push
```

## 前置条件

- 使用 Codex 后端命令需要安装 [Codex CLI](https://github.com/openai/codex)
- MCP 工具（fast-context, sequential-thinking）会随插件自动配置

## 许可证

MIT
