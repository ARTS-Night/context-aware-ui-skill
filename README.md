# Context-aware UI

**人間が読みやすく、使いやすく、内容が変わっても崩れないUIを作るための小さなAgent Skill。**

利用者の目的・情報の優先順位・適切な温度感を考え、AI生成でありがちな画一的な装飾を避けます。日本語の改行、長い文字列、画面幅変更で崩れる場合は、文字を隠さず、**CSSなどのレイアウト制約そのものを修正**します。

Web専用ではありません。CSSの具体策はWebの場合だけ適用します。**追加のPython、Playwright、ライブラリは不要**です。

> 試用版です。Skillを使えば必ず美しいUIになるという効果は、まだ実証していません。

## インストール（VS Code / Codex）

このリポジトリの**ルートがそのままSkill**です。複雑なセットアップは不要です。

### Windows PowerShell：全プロジェクトで使用

```powershell
New-Item -ItemType Directory -Force "$HOME/.agents/skills" | Out-Null
git clone https://github.com/ARTS-Night/context-aware-ui-skill.git "$HOME/.agents/skills/context-aware-ui"
```

macOS / Linux:

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/ARTS-Night/context-aware-ui-skill.git ~/.agents/skills/context-aware-ui
```

**更新はpullだけです。**

```powershell
git -C "$HOME/.agents/skills/context-aware-ui" pull --ff-only
```

初回のみcloneし、2回目からはpullしてください。古いZIPを手動配置した同名フォルダーがある場合は、先に別の場所へ退避してください。変更が認識されない場合はCodexセッションを再起動します。

### そのプロジェクトだけで使用

プロジェクトのルートで次を実行します。

```powershell
New-Item -ItemType Directory -Force ".agents/skills" | Out-Null
git clone https://github.com/ARTS-Night/context-aware-ui-skill.git ".agents/skills/context-aware-ui"
```

親プロジェクトでもSkillのバージョンをGit管理して共有したい場合は、通常のcloneの代わりにsubmoduleを使います。

```bash
mkdir -p .agents/skills
git submodule add https://github.com/ARTS-Night/context-aware-ui-skill.git .agents/skills/context-aware-ui
git commit -m "Add Context-aware UI skill"
```

他のPCでは親リポジトリを取得・pullした後、`git submodule update --init --recursive` を実行すると記録済みのSkill版が配置されます。最新版へ進めるときは `git submodule update --remote .agents/skills/context-aware-ui` を実行して、親リポジトリに変更をcommitします。通常のcloneとsubmoduleを**同じフォルダーで混用しない**でください。

## 使い方

Codexで `$context-aware-ui` を選び、次のように依頼します。

```text
$context-aware-ui
この画面を、人が読みやすく自然に使えるUIに改善してください。
日本語の長い文字列や画面サイズの変化でも崩れないようにし、
CSSの幅・最小サイズ・折返し・配置を原因から修正してください。
既存の機能とブランドを守り、意味のない装飾は増やさないでください。
```

新規UI制作でも、Web以外の画面でも利用できます。Skill本体は [SKILL.md](SKILL.md) の1ファイルのみです。

## English

A minimal, human-first Agent Skill for readable, intentional, resilient UI. It discourages generic AI-styled decoration and promotes fixing underlying layout constraints when Japanese or dynamic content wraps, clips, or overflows. Platform-agnostic; CSS guidance applies to web projects only.

## License

MIT — [LICENSE](LICENSE).
