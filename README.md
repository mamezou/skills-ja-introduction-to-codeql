# CodeQL を有効にしてソースコードを保護する（日本語版）

_安全でないコーディングパターンを特定し、解決して、再発を防ぐ方法を学ぶ。_

> このリポジトリは GitHub Skills「[Introduction to CodeQL](https://github.com/skills/introduction-to-codeql)」（MIT License）の日本語版です。
> 演習の進め方と自動チェックの仕組みは原本と同じで、Issue に投稿される手順の本文だけを日本語にしています。

## ようこそ

- **対象**: 開発者、セキュリティエンジニア、オープンソースのメンテナー
- **学ぶこと**: コードスキャンを有効にして SQL インジェクションなどの一般的な脆弱性を特定し、アラートを確認して修正する方法
- **作るもの**: 既存の脆弱性を特定し、本番コードで将来発生する脆弱性を防ぐ自動化されたプロセス
- **前提**:
  - [Introduction to GitHub](https://github.com/skills/introduction-to-github)
- **所要時間**: 30 分以内

### 演習の始め方

演習を自分のアカウントにコピーし、Octocat（Mona）が最初のレッスンを準備するまで **20 秒ほど**待ってから、
**ページを再読み込み**してください。

[![](https://img.shields.io/badge/Copy%20Exercise-%E2%86%92-1f883d?style=for-the-badge&logo=github&labelColor=197935)](https://github.com/new?template_owner=mamezou&template_name=skills-ja-introduction-to-codeql&owner=%40me&name=skills-introduction-to-codeql&description=Exercise:+Introduction+to+CodeQL&visibility=public)

<details>
<summary>うまくいかないとき 🤷</summary><br/>

演習をコピーするときは、次の設定を推奨します。

- Owner は自分の個人アカウント、またはリポジトリを置く Organization を選びます。
- private リポジトリは [Actions の実行時間](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions)を消費するため、public リポジトリを推奨します。

20 秒待っても演習が始まらない場合は、次の手順を行います。

1. 新しいリポジトリが作成されたら 20 秒ほど待ち、ページを再読み込みします。
2. リポジトリに作成された Issue の手順に従います。
3. ページが自動的に更新されない場合は、[Actions](../../actions) タブを確認します。
   - ジョブが実行中かどうかを確認します。完了まで時間がかかることがあります。
   - ジョブが失敗している場合は、講師に知らせてください。

</details>

---

&copy; 2026 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)
