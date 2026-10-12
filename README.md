# TokenCat

**Claude Code / Codex の残量を、メニューバーの猫で。**

TokenCat は macOS のメニューバーに住むドット絵の猫です。Claude Code と Codex の使用量（5時間枠・週次枠）に合わせて、猫がだんだん疲れていきます。数字を読まなくても、残りの余力がひと目でわかります。

![TokenCat](images/preview.png)

## ダウンロード

**[最新版をダウンロード (Releases)](https://github.com/karaageeeee/TokenCat-app/releases/latest)**

1. `TokenCat-<version>.dmg` を開き、`TokenCat.app` を「アプリケーション」へドラッグします。
2. TokenCat を起動すると、メニューバーに猫が現れます。

- 無料です。
- 動作環境: macOS 14 (Sonoma) 以降、Apple Silicon (M1 以降) の Mac。
- Apple の公証 (Notarization) 済みなので、そのまま開けます。
- Claude Code または Codex CLI に、あらかじめログインしておいてください。

## できること

| 使用量をひと目で | 並列で動かすAIを采配 |
| --- | --- |
| ![使用量](images/popover.png) | ![AIセッション](images/sessions.png) |

- **残量で猫の様子が変わる**: 元気 → 少し疲れ気味 → 眠そう → へとへと → ぐったり
- **Claude Code と Codex を同時に表示**: 5時間枠・週次枠の使用率と、リセットまでの残り時間
- **AIセッションの采配ビュー**: 複数の Claude Code / Codex セッションが「仕事中・応答待ち・待機」のどれかを一覧表示。応答待ちのAIをすぐ見つけられ、作業が終わると通知します
- 状態が変わったときの macOS 通知、更新間隔の設定、ログイン時の自動起動
- 日本語 / 英語

### AIセッション連携のセットアップ

ポップオーバーの「AIセッション」タブで「AIセッション連携をセットアップ」を押すと、Claude Code (`~/.claude/settings.json`) と Codex (`~/.codex/hooks.json`) にフックが追加されます。既存の設定は残したまま、TokenCat 用の項目だけを追記します。

## プライバシーとセキュリティ

TokenCat は外部に独自のサーバーを持たず、データを収集しません。

- **Claude Code の使用量**: Claude Code が macOS キーチェーンに保存しているログイン情報を読み取り、Anthropic の使用量API (`api.anthropic.com`) にだけ HTTPS で問い合わせます。初回起動時にキーチェーンへのアクセス許可を求められることがあります。
- **Codex の使用量**: インストール済みの `codex` コマンド (`codex app-server`) から取得します。
- **AIセッション連携**: フックからの通知は `127.0.0.1`（自分のMac内）だけで受け取ります。通知には `~/.tokencat/token` に保存したランダムな合言葉が必要で、このファイルは本人だけが読めます。
- 公開前に、ローカル通信部分を中心としたセキュリティレビューを実施しています。

脆弱性を見つけた場合は、公開の Issue ではなく GitHub の [Security Advisory](https://github.com/karaageeeee/TokenCat-app/security/advisories/new) からご連絡ください。

## 不具合・要望

[Issues](https://github.com/karaageeeee/TokenCat-app/issues) へどうぞ。

---

TokenCat は個人開発のアプリで、Anthropic および OpenAI とは関係ありません。Claude は Anthropic の、Codex は OpenAI の商標です。
