# Skill Scout

> 搜索 GitHub 高星 AI Agent 编码技能/规则项目，列表选装。两次确认，不自动安装。
> Scout GitHub for high-star AI agent coding skills/rules, pick and install. Two-step confirmation, never auto-install.

<p align="center">
  <b>默认中文</b> · <a href="#english">English</a>
</p>

---

## 这是什么

Skill Scout 是一个 **AI Agent 技能发现与安装工具**。帮你搜索 GitHub 上 20k+ stars 的 agent 编码技能/规则项目，列出供你选择，确认后自动安装到全局和/或当前项目。

## 它能解决什么

- GitHub 上 agent skill 项目太多了，不知道哪些靠谱
- 星数高的不一定适合装（合集、平台、安全专项要过滤）
- 装完还得手动适配中文、适配不同 agent 工具

Skill Scout 帮你：**搜 → 过滤 → 展示 → 等你选 → 等你定位置 → 装**

## 效果展示

```
用户: 找高星 skill

Skill Scout:
  搜索 GitHub 20k+ stars agent 技能项目...

  发现 5 个可安装项目：

  | # | 项目 | 星 | 类型 | 简介 |
  |---|------|----|----|------|
  | 1 | obra/superpowers | 245k | 技能包 | Agent 技能框架与开发方法论 |
  | 2 | addyosmani/agent-skills | 68k | 技能包 | 生产级工程技能 24 个 |
  | 3 | Leonxlnx/taste-skill | 55k | 技能包 | 防丑 UI，阻止模板化界面 |
  | 4 | NeekChaw/RIPER-5 | 2.6k | 协议 | 5 模式行为协议 |
  | 5 | Kulaxyz/self-learning-skills | 778 | 技能 | 自动收割黄金路径 |

  回复编号选择，如 "1 3 5" 或 "全部"

用户: 1 2

Skill Scout:
  安装到哪？
  1. 全局（所有 Hermes 会话可用）
  2. 当前项目（.cursor/rules/ + AGENTS.md）
  3. 都要

用户: 3

Skill Scout:
  正在安装...
  ✅ obra/superpowers → verification-before-completion (全局 + .cursor/rules/)
  ✅ addyosmani/agent-skills → doubt-driven-development (全局 + .cursor/rules/)
  完成。
```

## 用到的技术

- GitHub API 搜索 + 过滤
- 自动适配：Hermes skill 格式 / Cursor .mdc 格式 / AGENTS.md
- 中文提炼：原版英文内容自动转中文精华版

## 安装

### Hermes 全局安装

```bash
# 已安装到 ~/.hermes/skills/software-development/skill-scout/
# 加载后说 "skill-scout" 或 "找高星 skill"
```

### 手动使用

```bash
export https_proxy=http://127.0.0.1:7890

# 搜索 20k+ stars agent 技能
curl -s "https://api.github.com/search/repositories?q=agent+skills+coding+stars:>20000&sort=stars&per_page=20"
```

## 搜索关键词

| 关键词 | 命中类型 |
|--------|---------|
| `agent skills coding` | 通用技能包 |
| `agent rules cursor` | Cursor 规则 |
| `AGENTS.md rules` | 跨 agent 规则 |
| `claude code skills` | Claude Code 技能 |
| `coding agent discipline` | 行为协议 |

## 过滤规则

| 保留 | 排除 |
|------|------|
| 可安装规则文件 | 完整 agent 平台（ECC, DeerFlow） |
| 可安装技能包 | 纯合集（awesome-* 系列） |
| 紧凑行为协议 | 非编码类（安全攻防、法律） |
| | 作者已弃用 |

## 已知高星项目

| 项目 | 星 | 已收录 |
|------|----|:--:|
| obra/superpowers | 245k | ✅ |
| addyosmani/agent-skills | 68k | ✅ |
| Leonxlnx/taste-skill | 55k | ✅ |
| PatrickJS/awesome-cursorrules | 40k | 合集 |
| ciembor/agent-rules-books | 2k | ✅ |
| NeekChaw/RIPER-5 | 2.6k | ✅ |
| Kulaxyz/self-learning-skills | 778 | ✅ |
| entropyvortex/meta-llm-charter | 245 | ✅ |
| sisyphusse1-ops/claude-code-pro-pack | 30 | ✅ |
| madebyaris/advance-minimax-m3-cursor-rules | 124 | ✅ |
| intellectronica/ruler | 2.7k | ✅ |

---

## English

### What

Skill Scout discovers and installs high-star AI agent coding skills/rules from GitHub. Search → filter → list → **you pick** → **you choose target** → install.

### Why

- Too many agent skill repos on GitHub, hard to tell which are good
- High stars doesn't mean installable (collections, platforms, security-only)
- Manual adaptation for Chinese and different agent tools is tedious

### How

1. Multi-keyword GitHub API search (20k+ stars default)
2. Filter out platforms, collections, non-coding repos
3. Present ranked table, wait for user selection
4. Ask install target: global / project / both, wait for confirmation
5. Install with auto-adaptation (Hermes skill / Cursor .mdc / AGENTS.md)

### Keywords

`agent skills coding` · `agent rules cursor` · `AGENTS.md rules` · `claude code skills` · `coding agent discipline`

### Filter Rules

Keep: installable rules, skill packs, compact protocols
Skip: platforms (ECC, DeerFlow), awesome-lists, security-only, deprecated
