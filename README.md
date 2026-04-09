<div align="center">
  <h1>🚀 日本最強の「GitHub Copilot 活用プロジェクトテンプレート」を作る</h1>

最近、AI関連の情報のキャッチアップできてますか？

私は正直、各社AIのアップデートが早すぎてついていけてません。

しかもネットやGithubを検索しても英語の記事ばかりで読む気にもなれません。

そんな時に、「日本人用のテンプレートリポジトリ作ってみんなにプルリク出して貰えば最強のリポジトリできるのでは？」

と思い、このリポジトリを作るに至りました。

少しでも共感してくださった方は、じゃんじゃんプルリクを出してほしいです。

みんなで力を合わせて、誰もがAIの機能を最大限活かして開発できるリポジトリを作りませんか？
</div>

## ディレクトリ構成 (Directory Structure)

```text
.
├── .github/
│   ├── agents/                   # カスタムエージェントの役割とプロンプト定義 (`*.agent.md`)
│   ├── instructions/             # 特定のパスごとに適用されるカスタムインストラクション (`*.instructions.md`)
│   ├── skills/                   # エージェントに固有のタスクを実行させるスキルセット (`SKILL.md`)
│   ├── workflows/                # Copilot Cloud Agent等の環境構築向けCI/CD設定 (`copilot-setup-steps.yml`)
│   ├── copilot-instructions.md   # リポジトリ全体に適用される基本のAIプロンプト設定
│   └── COPILOT_USAGE.md          # 導入・運用に向けた各ファイルと機能の使い分けガイド
├── AGENTS.md                     # プロジェクト開始時にAIエージェントに提示する開発環境・コマンド等の一覧
└── README.md                     # (このファイル)
```

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
