# parable-fiction

一个用于写作**超短篇中文哲学寓言小说**的 Agent Skill，遵循开放的 SKILL.md 标准，可在 Claude、Codex、Cursor、Gemini CLI 等多种 AI agent 中使用。

给它一个抽象命题——「人总在两个选择之间徘徊」「神给了人一个无法验证的礼物」——它会把命题落成一个可以走进去的具体处境，写成 800—2500 字的短篇。

---

## 这个 skill 做什么

超短篇哲学寓言不是在讲道理，而是构建一个**让读者亲身进入的处境**，让命题从处境内部自然生长出来。这个 skill 把这套写法拆成了可执行的步骤：

- **提炼核心困境** — 把主题压缩成一句「一个人面对……，他无法……，但又不得不……」
- **确定载体意象** — 抽象命题必须有具体的物质形象承载，且贯穿全文
- **四段结构** — 降落 → 遭遇 → 内部震荡 → 开放的动作，每段给了篇幅比例
- **语言风格约束** — 句式节奏、意象密度、叙述者的克制
- **禁止清单** — 直接说出道理、用梦解释一切、感叹句收尾等常见陷阱
- **文风对齐** — 提供范文时，从四个维度拆解并对齐

参照谱系：卡夫卡、博尔赫斯、加缪、川端康成掌小说、史铁生。

---

## 安装

### Claude（网页版 / 桌面版）

下载 [`parable-fiction.skill`](./parable-fiction.skill)，在对话框里上传该文件，点击 **Save skill**。

### Claude Code

```bash
git clone https://github.com/doristt505/parable-fiction.git
mkdir -p ~/.claude/skills
cp -r parable-fiction/parable-fiction ~/.claude/skills/
```

### Codex（CLI / IDE 扩展 / 桌面版）

Codex 会扫描 `~/.agents/skills/`（个人跨仓库）和 `$REPO_ROOT/.agents/skills/`（项目级）。写作类 skill 建议装在个人目录：

```bash
git clone https://github.com/doristt505/parable-fiction.git
mkdir -p ~/.agents/skills
cp -r parable-fiction/parable-fiction ~/.agents/skills/
```

Codex 会自动检测新 skill；若未生效，重启 Codex。

### Cursor / Gemini CLI / 其他支持 SKILL.md 的 agent

把 `parable-fiction/` 这个文件夹放进该工具的 skills 目录即可，格式通用无需修改。

### ChatGPT 网页版 / 任意聊天界面

不支持自动加载的界面，用 [`prompt.md`](./prompt.md) —— 那是去掉 frontmatter 的纯提示词版本。整段复制，粘贴进「自定义指令」「系统提示」或项目说明里。代价是失去自动触发，需要手动说明要用这套写法。

---

## 用法

安装后直接提出创作需求，skill 会自动触发：

```
写一篇关于「一个人得到了足够的，却不知道足够是否真的足够」的寓言

把这个思想实验写成小说：忒修斯之船，但换的是记忆

写一个超短篇，卡夫卡风格，主题是等待一封永远不会到的信
```

也可以附上参考文风，skill 会从句长、意象密度、叙述者距离、结尾处理四个维度对齐。

---

## 不适用于

- 有完整情节弧、人物成长、冲突解决的常规短篇小说
- 散文诗
- 非虚构哲学写作

---

## 结构

```
parable-fiction/
├── README.md
├── LICENSE
├── prompt.md                  # 通用提示词版（无 frontmatter）
├── parable-fiction.skill      # 打包版，供 Claude 一键安装
└── parable-fiction/
    └── SKILL.md               # 主文件
```

---

## License

MIT
