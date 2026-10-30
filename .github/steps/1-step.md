## Step 1: コードスキャンを有効にする

[CodeQL](https://codeql.github.com/) によるコードスキャンの概要と、コードの保護にどのように役立つかを学びます。

### GitHub のコードスキャンとは

[コードスキャン](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning)は、
[GitHub Advanced Security（GHAS）](https://docs.github.com/ja/get-started/learning-about-github/about-github-advanced-security)製品群の一部です。
開発チームがコードをリリースする既存のプロセスに、セキュリティテストツールを直接組み込めます。
静的アプリケーションセキュリティテスト（SAST）、コンテナー、Infrastructure as Code など、多くの種類に対応しています。
分析結果はコードと並べて GitHub 上に表示できます。作業画面を切り替える必要はありません！ 🎉

> [!TIP]
> GitHub Advanced Security の全機能は、public リポジトリでは無料です。ただし、private リポジトリでは対応する[有料アカウント](https://docs.github.com/ja/billing/managing-billing-for-your-products/managing-billing-for-github-advanced-security/about-billing-for-github-advanced-security)が必要です。

### CodeQL とは

[CodeQL](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql)は、
SQL インジェクション、クロスサイトスクリプティング、コードインジェクションなどのセキュリティ上の弱点を特定する静的解析テストツールです。

通常、CodeQL の[クエリ](https://codeql.github.com/docs/writing-codeql-queries/about-codeql-queries/)は、複数のパターンを検出できるように
[クエリスイート](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql#about-codeql-queries)にまとめられます。
クエリを適切に組み合わせると、強力な分析が可能です。セキュリティ専門家のチームが、一般的な利用場面とプログラミング言語に対応する
クエリスイートをあらかじめ用意しています。

多くの場合、既定のクエリスイートを選ぶだけで CodeQL を利用できます。拡張クエリスイートを選んだり、
[GitHub Actions]() を使って独自のクエリスイートを設定したりすることもできます。

<img width="250" align="right" alt="CodeQL の既定の設定画面" src="../images/codeql-default-configuration-box.png"/>

既定の設定には、次の選択肢があります。

- **Languages:** 対応する言語をリポジトリから自動的に検出し、スキャンを有効にします。

- **Query suites:** 使用する検出パターンのスイート一覧です。**Default** または **Extended** が自動的に用意されます。

- **Runner type:** CodeQL 分析を実行する GitHub Actions ランナーの種類です。既定では標準の GitHub-hosted runner を使用しますが、
  [self-hosted runner](https://docs.github.com/ja/enterprise-cloud@latest/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/configuring-code-scanning-for-your-appliance)を使用するように変更できます。

- **Events:** CodeQL スキャンを実行するトリガーです。本番コードでは、マージ前と定期スケジュールで実行するのが一般的です。

### ⌨️ やること: CodeQL でコードスキャンを有効にする

1. ブラウザーで別のタブを開き、演習用リポジトリを表示します。**Code** タブを開いていることを確認します。

1. 上部のナビゲーションで **Settings** タブを選びます。

1. 左側のナビゲーションのセキュリティ設定で **Advanced Security** を選びます。
   アカウントによっては **Code security** と表示されます。

1. 下へスクロールして **Code scanning** の領域を探します。

1. **CodeQL** の設定で **Set up** ドロップダウンメニューをクリックし、**Default** を選びます。

   <img width="400" alt="コードスキャンを有効にする画面" src="../images/enable-code-scanning.png"/>

1. **Enable CodeQL** をクリックします。

   > 💡 ヒント: CodeQL の最初の実行が開始されます。進行状況は **Actions** タブで確認できます。

1. CodeQL を有効にしたので、Mona が作業を確認しています。少し待って、コメントを見てください。進捗と次の Step が投稿されます。
