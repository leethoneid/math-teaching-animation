# math-teaching-animation（Antigravity 安装包）

为中学生把数学知识点或作业题做成可交互动画教学 HTML 的技能，遵循 Agent Skills 通用标准。

## 安装

### 从 GitHub 安装（推荐）

```bash
git clone https://github.com/leethoneid/math-teaching-animation-antigravity.git
mkdir -p ~/.gemini/antigravity/skills
cp -r math-teaching-animation-antigravity ~/.gemini/antigravity/skills/
```

个别版本的 Antigravity 编辑器改读 `~/.agents/skills`，如果上面那条路装完没生效，改用：

```bash
mkdir -p ~/.agents/skills
cp -r math-teaching-animation-antigravity ~/.agents/skills/
```

### 从 zip 安装（全局，所有项目可用）

```bash
unzip math-teaching-animation-antigravity.zip
mkdir -p ~/.gemini/antigravity/skills
cp -r math-teaching-animation ~/.gemini/antigravity/skills/
```

个别版本的 Antigravity 编辑器改读 `~/.agents/skills`，如果上面那条路装完没生效，改用：

```bash
mkdir -p ~/.agents/skills
cp -r math-teaching-animation ~/.agents/skills/
```

### 只给当前项目安装

```bash
unzip math-teaching-animation-antigravity.zip
mkdir -p .agents/skills
cp -r math-teaching-animation .agents/skills/
```

### 装完必做

重启 Antigravity 的 agent 会话，技能在会话启动时扫描，装完不重启不会生效。

## 使用

在 Antigravity 里直接提需求，例如：“用动画讲一下完全平方公式”或贴一道题，agent 会按 SKILL.md 的规矩生成单个离线可用的 HTML 教学页。

## 包内容

- `SKILL.md`：技能正文（带 name 与 description 的 frontmatter）
- `assets/example-meeting-point.html`：完整示例，汇合点最小路程问题
