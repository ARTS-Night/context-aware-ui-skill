# Context-aware UI

**A lightweight, platform-agnostic Agent Skill for human-centered UI/UX design judgment.**

This Skill helps coding agents decide *why* an interface should look, feel, and behave a certain way. It is not a UI template, component library, or browser automation bundle.

**Version: 0.4.1 (experimental).** The files have been structurally checked; improved design outcomes have not yet been demonstrated by controlled user studies.

## What it does

- Understand user goals, existing constraints, brand, and context before proposing a design.
- Evaluate emotional tone, information density, accessibility, visual expressiveness, and irreversible actions **independently**.
- Actively shape composition, information hierarchy, visual rhythm, and character rather than merely avoiding decoration.
- Protect information integrity, discoverability, feedback, error recovery, and safe interactions.
- Adapt thinking to **web, desktop, mobile, games, VR/AR, embedded, voice, and tactile interfaces** without claiming universal dimensions.
- Separate **A: aesthetic/context fit** from **B: functional, safety, and accessibility quality**.
- Use existing project tools for verification; never claim to have tested what was not actually tested.

No Python, Playwright, CSS framework, or external runtime dependency is required.

## Install

The repository root is the Skill directory: it contains `SKILL.md` and `references/`.

**Codex or compatible Agent Skills clients — install globally:**

macOS / Linux:
```bash
mkdir -p ~/.agents/skills
git clone --depth 1 https://github.com/ARTS-Night/context-aware-ui-skill.git ~/.agents/skills/context-aware-ui
```

Windows PowerShell:
```powershell
New-Item -ItemType Directory -Force "$HOME/.agents/skills" | Out-Null
git clone --depth 1 https://github.com/ARTS-Night/context-aware-ui-skill.git "$HOME/.agents/skills/context-aware-ui"
```

For project-specific use, copy `SKILL.md` and `references/` into `<project>/.agents/skills/context-aware-ui/`. Copy rather than committing a nested Git repository by accident. Restart the agent session if necessary; exact discovery behavior varies by client.

## Example prompts

```text
$context-aware-ui
Review this desktop application's UI. Recommend changes based on daily tasks,
user expertise, desired tone, information density, and interaction risks.
Respect the existing implementation and report unverified points.
```

```text
$context-aware-ui
Design a Japanese project dashboard. Choose a distinctive yet usable visual
composition; implement working interactions, keep metrics truthful, and
verify the states you can actually test.
```

```text
$context-aware-ui
Improve the interface for this VR editing tool. Consider viewing distance,
input methods, fatigue, and recovery rather than applying web pixel sizes.
```

For an A/B comparison, use identical starting content and instructions in separate sessions, with and without the Skill. Evaluate visual appeal and functionality **separately**.

## Contents

```text
SKILL.md
references/
  design-judgment.md
  interaction-and-quality.md
  platform-and-evidence.md
```

## 日本語

**Context-aware UI** は、特定のWeb技術に限定されないUI/UXの設計思考を支援するAgent Skillです。

「装飾を減らせば良いUIになる」「管理画面なら表だけでよい」などの固定観念を避け、人間の目的・温度感・情報密度・操作の重大性を分けて判断します。美しい構図・個性・リズムを積極的に考えながら、**操作できること・表示内容が正しいこと・危険な操作の安全性**も確認します。

VS CodeのCodexなどAgent Skills対応環境で `$context-aware-ui` を指定して利用できます（対応方法はクライアントによります）。

**試用版です。** Skillの利用によってUIの快適性や美観が必ず改善するという科学的な保証はありません。既存研究の適用条件は [根拠と限界](references/platform-and-evidence.md) を参照してください。

## License

[MIT](LICENSE). Contributions and reproducible comparison results are welcome.
