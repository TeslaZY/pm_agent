# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with this repository.

## Project Overview

**PM Agent (Product Manager Agent)** - 基于 [Anthropic Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) 方法论的产品经理工作流插件。

**核心理念：** 从产品想法到完整 PRD 和原型，专注需求收集、用户分析、功能设计和文档维护。

**Long-Running 模式：** 通过 `task-list.json` 和 `pm-progress.md` 跨多个上下文窗口保持连续性。

## Quick Reference

### 5 Commands

| Command | Purpose |
|---------|---------|
| `/pm:init` | Initialize new product project |
| `/pm:discover` | Collect requirements and user stories |
| `/pm:analyze` | Deep analysis with tough questioning |
| `/pm:design` | Create PRD and prototypes |
| `/pm:status` | View current project status |

### Workflow

```
/pm:init → /pm:discover → /pm:analyze → /pm:design → /pm:status (review)
```

### Phase Detection

| Condition | Phase |
|-----------|-------|
| No `Product-Spec.md` | Not Started |
| `Product-Spec.md` exists, no stories | Init Complete |
| User stories exist, no analysis | Discovery Complete |
| Analysis complete, no PRD | Analysis Complete |
| PRD and prototypes exist | Design Complete |

## Plugin Architecture

```
pm-agent/
├── CLAUDE.md                  # This file (project context)
├── agents/product-manager.md  # Agent execution logic
├── prompts/                   # Session prompts
│   ├── init-prompt.md         # Init phase guidance
│   └── discover-prompt.md     # Discovery phase guidance
├── commands/                  # 5 user commands (self-contained)
│   ├── init.md                # Project initialization
│   ├── discover.md            # Requirement discovery & user stories
│   ├── analyze.md             # Deep analysis & tough questioning
│   ├── design.md              # PRD generation & prototype design
│   └── status.md              # Project status review
└── docs/                      # Documentation
    └── templates/             # Task list & progress templates
```

每个 command 文件都是自包含的，包含完整的工作流程和能力定义。

## Dependencies

### Required
- **Pencil MCP** - For prototype design in `/pm:design`

### Recommended
- **Git** - For version control and document commits

### Detection
`/pm:init` automatically checks dependencies:
```
╔══════════════════════════════════════════════════════════════╗
║                 DEPENDENCY CHECK                            ║
╠══════════════════════════════════════════════════════════════╣
║ Pencil MCP:  ✓ Available / ✗ Not found                      ║
║ Git:         ✓ Available / ✗ Not found                      ║
╚══════════════════════════════════════════════════════════════╝
```

If Pencil MCP is missing, user can:
1. Continue with limited functionality (no prototypes)
2. Show installation guide
3. Abort and install first

## Key Principles

1. **task-list.json is truth** - Single source of truth for all tasks
2. **One phase at a time** - Complete each phase before moving on
3. **Document everything** - `pm-progress.md` is the memory between sessions
4. **User-centric** - Always focus on user needs and stories
5. **Iterate** - Refine through feedback and review
6. **Check dependencies first** - Ensure tools are available before proceeding

## References

- [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [agents/product-manager.md](agents/product-manager.md) - Detailed execution logic
- [docs/templates/](docs/templates/) - Task and progress templates
