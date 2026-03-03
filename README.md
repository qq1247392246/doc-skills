# DOC Skills

> 面向文档编程辅助工具 — 让需求讨论沉淀为可追溯的结构化文档

## ✨ 特性

- **零依赖** - 纯提示词实现，无需安装运行环境
- **极简安装** - 手动复制两个文件即可使用
- **无缝集成** - 命令触发 + AI 自动识别，无感使用
- **智能回查** - 自动关联历史文档，保持上下文连贯

## 📦 安装

### 1. 下载项目

```bash
git clone https://github.com/yourusername/doc-skills.git
cd doc-skills
```

### 2. 复制到配置目录

**Claude Code 用户：**

```bash
mkdir -p ~/.claude/skills/doc
cp skill.md ~/.claude/skills/doc/
cp -r templates ~/.claude/skills/doc/
```

**Codex 用户：**

```bash
mkdir -p ~/.codex/instructions/doc
cp skill.md ~/.codex/instructions/doc/
cp -r templates ~/.codex/instructions/doc/
```

完成！重启 Claude Code / Codex 后即可使用。

## 🚀 使用

安装后，Claude / Codex 会自动识别以下命令：

| 命令 | 功能 |
|------|------|
| `/doc [主题]` | 启动新主题文档模式 |
| `/doc list` | 查看所有主题及状态 |
| `/doc open [主题]` | 继续旧主题，AI 主动摘要 |
| `/doc del [主题]` | 删除主题及文档 |

## 📁 文档结构

```
doc/
├── INDEX.md                    # 自动维护的索引
└── YYYY.MM.DD主题名/            # 主题文件夹
    ├── 主题名需求文档.md        # 需求、逻辑、思路
    └── 主题名设计文档.md        # 实现设计、验收条件
```

## 🔧 工作流

```
方式 C（命令触发）：

用户: /doc 实时数据处理优化
AI:  已创建主题「实时数据处理优化」，请描述您的需求...

方式 B（AI 识别）：

用户: 我想做一个实时数据处理的功能...
AI:  检测到您可能在讨论新需求，是否启动文档模式？
用户: 是的
AI:  已创建主题「实时数据处理优化」...

共同流程：

用户: [描述需求]
AI:  [关键点回查]参考「XX」文档...
     [质疑]关于XX，请确认：1... 2...

用户: [回答问题]
AI:  需求已明确，是否确认？

用户: 确认
AI:  已生成设计文档，可以开始实现了
```

## 📄 项目结构

```
doc-skills/
├── skill.md          # ⭐ 核心技能文件
├── templates/        # 文档模板
│   ├── req.md
│   └── design.md
└── README.md         # 本文件
```

只需复制 `skill.md` 和 `templates/` 到 Claude/Codex 配置目录即可使用。

## 📝 模板自定义

修改 `templates/` 下的文件即可自定义文档模板：
- `req.md` - 需求文档模板
- `design.md` - 设计文档模板

## 📜 License

MIT
