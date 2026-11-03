# Context-aware UI

A **small, practical Agent Skill** for readable, human-friendly interfaces that remain usable as content and layout change.

**What it emphasizes:** visual hierarchy, intentional visual character instead of generic AI-looking design, Japanese/CJK text handling, responsive layout, and fixing the **underlying CSS constraints** behind overlap, clipping, and overflow.

The Skill is platform-agnostic. Its CSS guidance applies only when the project uses CSS. No Python, Playwright, or additional runtime dependencies are required.

## Why is SKILL.md written in English?

The instructions use English for consistent technical terminology and concise agent-facing wording. **There is no verified guarantee that English instructions outperform Japanese instructions in Codex.** The `description` includes Japanese trigger terms, and the instructions explicitly preserve the user's language and require testing Japanese/CJK content. English instructions do **not** mean English UI labels.

The Skill is intentionally just one `SKILL.md` file. Readability and actual results matter more than its language or file size.

## Installation (VS Code / Codex)

This repository's **root is the Skill folder**. You can clone it directly without copying files.

**Windows PowerShell — user-wide:**

```powershell
New-Item -ItemType Directory -Force "$HOME/.agents/skills" | Out-Null
git clone https://github.com/ARTS-Night/context-aware-ui-skill.git "$HOME/.agents/skills/context-aware-ui"
```

**macOS / Linux — user-wide:**

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/ARTS-Night/context-aware-ui-skill.git ~/.agents/skills/context-aware-ui
```

**Update an existing Git clone:**

```powershell
git -C "$HOME/.agents/skills/context-aware-ui" pull --ff-only
```

Clone once, then pull for updates. If you previously copied an older version manually, back up or remove that folder before cloning. Restart the Codex session if the changes are not detected.

**Project-local:** run `git clone https://github.com/ARTS-Night/context-aware-ui-skill.git .agents/skills/context-aware-ui` from the project root, after creating `.agents/skills` if needed. If you need the version to be tracked by the parent repository and reproducible after pull, use a Git submodule rather than committing a nested clone.

## Usage

In Codex, mention `$context-aware-ui`:

```text
$context-aware-ui
Improve this Japanese UI so it reads naturally and remains stable with long
text, changing data, and narrow windows. Fix underlying CSS sizing, wrapping,
or positioning problems instead of hiding overflow. Preserve the product's
identity and existing functionality.
```

## 日本語

**人間にとって自然に見やすく、使いやすいUIを作るための最小限のSkill**です。英語を中心に書いていますが、日本語UIを英語化することはありません。

情報の優先順位・文字・余白・構図・温度感を考え、理由のないグラデーションや画一的なカードの多用を避けます。日本語の折り返し、長いURL、動的な文字数の変化で崩れた場合は、`overflow: hidden`で隠さず、Flex/Gridの幅・最小サイズ・固定高さなどの原因から修正します。

既にインストールしてある場合は、上記の`git pull --ff-only`で更新できます。

**注意:** これは試用版です。英語と日本語の指示文による性能差や、Skill導入による美観・使いやすさの改善は、まだ統制された実験で実証していません。

## License

MIT — [LICENSE](LICENSE).
