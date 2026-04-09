# copilot_best_practice
🚀 このリポジトリは2026年4月時点でのGitHub Copilotの運用に必要な.github/ 配下でのおすすめファイル構成です。

## 📚 参考資料 (References)
これまでのカスタムエージェント（`.agent.md`）、リポジトリ全体カスタムインストラクション（`.github/copilot-instructions.md`）、パス別カスタムインストラクション（`.instructions.md`）、エージェントスキル（`SKILL.md`）、およびクラウドエージェントワークフロー（`copilot-setup-steps.yml`）の設計・定義において参考にした公式ドキュメントおよび関連リソースです。

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
  - （ディレクトリ構造、YAMLフロントマター、スクリプト実行時の `allowed-tools` を用いた自動承認設定などの実践的作成方法）

### ☁️ Copilot Cloud Agent ワークフロー (.github/workflows/copilot-setup-steps.yml)
- [Adding GitHub Copilot cloud agent to your organization - GitHub Docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/add-copilot-cloud-agent)
  - （GitHub Copilot Cloud Agentの導入方法全般について）
- [Configuring runners for GitHub Copilot cloud agent in your organization - GitHub Docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/configure-runner-for-coding-agent)
  - （`copilot-setup-steps.yml` を用いた依存関係の自動インストール、専用ジョブの構成ルール、使用可能な属性などの公式要件）
