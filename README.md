[中文](README_CN.md) | English

## math-teaching-animation (Agent Skills package)

Turns a math concept or homework problem into an interactive animated teaching HTML page, following the Agent Skills open standard (a folder containing SKILL.md). Works with any SKILL.md-compatible client, including Antigravity, Claude Code, Codex, Gemini CLI, and Cursor — not Antigravity only.

## Installation

Generic method: clone this repo, copy the whole folder into your client's skills directory, and restart the agent session.

```bash
git clone https://github.com/leethoneid/math-teaching-animation.git
```

Install commands (pick one for your client; copy the whole folder):

```bash
# Antigravity (global)
mkdir -p ~/.gemini/antigravity/skills
cp -r math-teaching-animation ~/.gemini/antigravity/skills/
# Claude Code (global)
mkdir -p ~/.claude/skills
cp -r math-teaching-animation ~/.claude/skills/
# Codex (global)
mkdir -p ~/.codex/skills
cp -r math-teaching-animation ~/.codex/skills/
# Gemini CLI (global)
mkdir -p ~/.gemini/skills
cp -r math-teaching-animation ~/.gemini/skills/
# Current project only (Antigravity example)
mkdir -p .agents/skills
cp -r math-teaching-animation .agents/skills/
```

| Client | Global (whole machine) | Current project only |
| --- | --- | --- |
| Antigravity | `~/.gemini/antigravity/skills/` | `.agents/skills/` |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| Codex | `~/.codex/skills/` or `~/.agents/skills/` | `.codex/skills/` or `~/.agents/skills/` |
| Gemini CLI | `~/.gemini/skills/` | `.gemini/skills/` |
| Cursor | — (project only) | `.cursor/skills/` |
| Muse | workspace `custom-skills/` directory | — |

Three notes: copy the whole folder (it contains SKILL.md and assets), not just SKILL.md alone; some Antigravity versions read `~/.agents/skills` instead — switch to that directory if the above path doesn't take effect; restart the agent session after installing, since skills are scanned at session startup.

To update: `git pull` inside the cloned repo, then copy again.

## Usage

After installing and restarting the session, just ask in natural language, and the skill will generate a single offline HTML teaching page following SKILL.md:

- Concept walkthrough: "Explain the perfect square formula with an animation"
- Problem walkthrough: paste a problem and ask the agent to teach it with an animation

Explicit invocation (optional, not required): `/math-teaching-animation` in Claude Code, `$math-teaching-animation` in Codex; in other clients just ask — the skill triggers automatically from its description.

Output standard: a single self-contained HTML file — double-click to open in a browser, no build step, no sign-in, no internet; play, pause, step forward, step back, and reset controls plus sliders for key parameters; one consistent color scheme across the page: known quantities in blue, unknowns in orange, conclusions in green.

## Examples

![Meeting-point problem statement](assets/meeting-point-problem.png)

![Meeting-point example](assets/meeting-point-preview.gif)

- The first image above is the original problem statement; the second is the animation. Its reproduction prompt: see `meeting-point-prompt.md` (prompt in Chinese) — send the prompt to an agent with this skill installed to generate a similar page.
- Included in this repo: `assets/example-meeting-point.html` — the meeting-point minimum-total-distance problem (four neighborhoods on a street, weighted distance sum minimized). Open it directly in a browser to see the finished page and compare it with the teaching approach and implementation.
- Concept example: "Explain the perfect square formula with an animation" → area model + sliders for a and b, showing how (a+b)² expands.

## Contents

- `SKILL.md`: the skill itself (name and description frontmatter)
- `assets/example-meeting-point.html`: complete example, the meeting-point minimum-distance problem
