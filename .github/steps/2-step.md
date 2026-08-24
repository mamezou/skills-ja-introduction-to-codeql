## Step 2: pull request で脆弱性を検出する

コードスキャンの動作を確認するため、`routes.py` ファイルに脆弱性を作り、アラートを発生させます。

### ⌨️ やること: 脆弱性を作る

1. 上部のナビゲーションで **Code** タブを選びます。

1. `server` フォルダーに移動し、`routes.py` ファイルを選びます。

1. プレビューの右上にある **Edit** ボタンをクリックします。

   <img width="500" alt="Edit ボタン" src="../images/edit-button.png"/>

1. **16 行目**付近に移動し、次の内容に変更します。

   ```py
   "SELECT * FROM books WHERE name LIKE '%" + name + "%'"
   ```

1. エディター右上の **Commit changes...** ボタンをクリックします。表示された画面で **Create a new branch** のラジオボタンを選びます。
   **main ブランチにはコミットしないでください。**

1. **Propose changes** を選び、**Create pull request** をクリックします。ブランチ名には次の文字列を使用します。

   ```txt
   learning-codeql
   ```

1. 新しく表示されたページで、pull request の説明の下にある **Create pull request** ボタンを押します。

### ⌨️ やること: pull request を確認する

1. 必要に応じて、前の操作で作成した pull request を開きます。

1. pull request の一番下までスクロールし、`CodeQL` という名前のチェックを探します。pull request で提案されたコードの変更をスキャンする分析ジョブです。

   <img width="500" alt="実行中の CodeQL チェック" src="../images/codeql-check-in-progress.png" />

1. ジョブがまだ実行中の場合は、完了するまで数分待ちます。

1. コメントの中から分析結果を探します。
   - SQL インジェクションの脆弱性が検出され、修正案も示されていることを確認します。
   - 現時点では、コメントへの対応や問題の解決は必要ありません。

   <img width="500" alt="コードスキャンの結果" src="../images/code-scan-results.png" />

   > 💡 ヒント: **Show paths** リンクをクリックすると、ユーザー入力（source）からアプリケーション内を通り、処理される場所（sink）まで、アラートに関係するデータの流れを詳しく確認できます。

### ⌨️ やること: CodeQL のスキャンログを表示する

1. 上部のナビゲーションで **Actions** タブを選びます。

1. 左側のナビゲーションで **CodeQL** を選び、ワークフローの実行を絞り込みます。

   <img width="500" alt="CodeQL の絞り込み" src="../images/codeql-filter.png"/>

1. **PR #2** という名前のワークフロー実行をクリックし、詳細ページを開きます。

   <img width="500" alt="CodeQL の設定" src="../images/codeql-pr2.png"/>

1. **Show all jobs** をクリックして実行ジョブを展開し、**Analyze (python)** をクリックします。ワークフローの全 Step が表示されます。

   <img height="250" alt="マトリックスジョブ" src="../images/matrix-jobs.png" />

   <img height="250" alt="CodeQL ジョブの一覧" src="../images/list-of-codeql-jobs.png" />

1. 分析の項目を探し、必要に応じてログを確認します。

   <img width="500" alt="Python 分析のログ" src="../images/python-analysis-logs.png" />

1. pull request を作成して CodeQL スキャンが完了したので、Mona が作業を確認しています。少し待って、コメントを見てください。進捗と次の Step が投稿されます。

> [!TIP]
> コードスキャンを pull request に組み込む方法について詳しくは、[pull request のコードスキャンアラートをトリアージする](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/triaging-code-scanning-alerts-in-pull-requests)ページを参照してください。
