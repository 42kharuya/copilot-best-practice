<div align="center">
  <h1>🚀 日本最強の「GitHub Copilot 活用プロジェクトテンプレート」を作る</h1>
  <p><b>AIの進化スピードに、チーム全員でサバイブするための「集合知」リポジトリ</b></p>
</div>

日々のAIツールの進化はあまりにも早く、最新のベストプラクティスは英語圏に散在しています。
これを個人の力だけでキャッチアップし、現場のプロジェクトに落とし込むのはもはや限界にきています。

そこで、**「日本の現場ですぐに使える、GitHub Copilotの最強のテンプレート」**をみんなの力で作りませんか？

このリポジトリには、GitHub Copilotをしゃぶり尽くすための以下の骨組みをすでに用意しています。
- 💬 **対話ルール**: 全体ルールと局所ルールを分けて管理できる構成
- 🤖 **カスタムエージェント**: レビューやテスト生成に特化したAI同僚
- 🛠️ **スキル / ワークフロー**: エージェント実行やクラウド環境構築を支える拡張ポイント

「うちの現場ではこういうプロンプトを使っている」
「この設定（.instructions.md）を追加したら劇的に精度が上がった」

そんな皆さんの実践的な知見を、ぜひPull Requestで共有してください。
属人化しがちなAI活用のノウハウをここに集約し、誰もが**初日からAIのポテンシャルを120%引き出せるベースキャンプ**を一緒に作り上げましょう！

## このリポジトリの戦略

このリポジトリは、**あらゆるプロジェクトで共通な部分だけを完成版として持ち、プロジェクトごとに変わる部分は差し替えやすくする**ことを重視しています。

要するに、**「全部入りテンプレート」ではなく、「ブレない骨格 + 差し込み設計」**を提供する方針です。

### 3つのレイヤー

| レイヤー | 役割 | 何を置くか |
| :--- | :--- | :--- |
| **Core** | どのプロジェクトでも変わりにくい共通原則 | `AGENTS.md`, `.github/copilot-instructions.md` |
| **Slots / Blueprints** | プロジェクトごとに差し替える場所を明確化する | 記入ガイド付きテンプレート、`.example`、使い分けガイド |
| **Optional Packs** | 必要な人だけ使う具体例や拡張 | スタック別サンプル、ケーススタディ、発展的な workflow |

### なぜこの形にするのか

- **普遍部分**を完成版にすると、初見でもすぐ使える
- **可変部分**を無理に完成版にしないことで、どんなプロジェクトにも持ち込みやすい
- 技術スタック別の具体例は本体から切り離すことで、汎用性と実用性を両立できる

### このリポジトリで完成版にするもの

- AIの振る舞い原則
- 出力ブレを減らすルール
- 変更時の安全性ルール
- どこに何を書くべきかの整理

### このリポジトリで「差し込み」にするもの

- 技術スタック
- ディレクトリ構造
- ビルド / テストコマンド
- アーキテクチャや命名規約
- チーム固有ルール

初見の人向けに一言で言うと、

> **このリポジトリは、GitHub Copilot を高精度・低ブレで使うための共通OSと、その上に各プロジェクトの事情を安全に差し込むための設計集です。**

## ディレクトリ構成 (Directory Structure)

```text
.
├── .github/
│   ├── about/                    # 各機能・各ファイルの詳細説明
│   ├── agents/                   # 実際に有効化するカスタムエージェント定義
│   ├── blueprints/               # コピーして使う雛形群 (`*.example`)
│   ├── instructions/             # 実際に有効化するパス別 instructions
│   ├── optional-packs/           # 必要な人だけ追加する具体例や拡張
│   ├── skills/                   # 実際に有効化する skills
│   ├── workflows/                # 実際に有効化する workflows
│   ├── copilot-instructions.md   # リポジトリ全体に適用する共通ルール
│   └── COPILOT_USAGE.md          # 全体像と使い分けの概要ガイド
├── AGENTS.md                     # どのプロジェクトでも使いやすい共通原則
└── README.md                     # (このファイル)
```

## このテンプレートの使い方

1. まず `AGENTS.md` と `.github/copilot-instructions.md` を **Core** として使う
2. プロジェクト固有情報を入れるときは `.github/blueprints/project-context/` のチェックリストと雛形から始める
3. 必要な雛形を `.github/blueprints/` から選んで、実際の配置先へコピーする
4. 特定用途の具体例が必要なら `.github/optional-packs/` を追加で使う
5. 詳しい使い方は `.github/about/` を参照する

## 📕 参考資料 (References)

### 🤖 AGENTS.md (AIコーディングエージェント向け README)
- [agentsmd/agents.md](https://github.com/agentsmd/agents.md)
  - （AIコーディングエージェントに向けた「エージェント版 README」として活用されるオープンな標準フォーマットとベストプラクティス）

### 🌟 リポジトリ全体カスタムインストラクション (.github/copilot-instructions.md)
- [Adding repository custom instructions for GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)
  - （リポジトリ全体に適用されるグローバルなカスタムインストラクションの作成と設定についての公式ガイドライン）

### 🤖 カスタムエージェント (.github/agents/*.agent.md)
- [About custom agents - GitHub Docs](https://docs.github.com/en/copilot/concepts/prompting/about-custom-agents)
  - （カスタムエージェントの概要、YAMLフロントマターの記述方法などの基本仕様）
- [agentsmd/agents.md](https://github.com/agentsmd/agents.md)
  - （エージェントの定義に用いられるMarkdownベースのファイルフォーマットの標準リポジトリ）

### 📝 パス別カスタムインストラクション (.github/instructions/*.instructions.md)
- [Adding repository custom instructions for GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)
  - （Globパターンを使った適用範囲の設定 `applyTo` や使用除外設定 `excludeAgent` などの構成方法の詳細）
- [About customizing GitHub Copilot responses - GitHub Docs](https://docs.github.com/en/copilot/concepts/prompting/response-customization)
  - （GitHub Copilotのレスポンスカスタマイズ全般に関する基本概念と優先順位の理解）

### 🧰 エージェントスキル (.github/skills/*/SKILL.md)
- [About agent skills - GitHub Docs](https://docs.github.com/en/copilot/concepts/agents/about-agent-skills)
  - （エージェントが専門タスクを実行する際に呼び出せる指示・スクリプト群 `SKILL.md` の概念と仕様・配置場所）
- [Creating agent skills for GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/cloud-agent/create-skills)
  - （ディレクトリ構造、YAMLフロントマター、などの実践的作成方法）

### ☁️ Copilot Cloud Agent ワークフロー (.github/workflows/copilot-setup-steps.yml)
- [Adding GitHub Copilot cloud agent to your organization - GitHub Docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/add-copilot-cloud-agent)
  - （GitHub Copilot Cloud Agentの導入方法全般について）
- [Configuring runners for GitHub Copilot cloud agent in your organization - GitHub Docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/configure-runner-for-coding-agent)
  - （`copilot-setup-steps.yml` を用いた依存関係の自動インストール、専用ジョブの構成ルール、使用可能な属性などの公式要件）
