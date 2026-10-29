## Step 3: CodeQL アラートを確認して対応を決める

pull request の変更を CodeQL で確認し、分析結果を表示できるようになりました。アラートの管理方法を学びます。

GitHub には、セキュリティに関係する問題を安全に管理する **Security and quality** タブがあります。
CodeQL は、多くの分析ツールと同じ標準形式でアラートを保存し、結果は **Code scanning** の領域に表示されます。

<img width="600" alt="Security and quality タブの概要" src="../images/security-tab-overview.png" />

### アラートにはどのような情報が表示されるか

アラートの主要部分には、対応状況、影響を受けるブランチ、コード上の場所、重大度や
[CVE 識別番号](https://docs.github.com/ja/code-security/security-advisories/working-with-repository-security-advisories/about-repository-security-advisories#cve-identification-numbers)などの分類情報が表示されます。

状況に関する情報の後には、問題の詳しい説明、推奨される解決策、変更案のコードが表示されます。

<img width="600" alt="アラートの追加情報" src="../images/additional-information.png"/>

### CWE とは

CodeQL がスキャンするパターンの多くは、既存の脆弱性データベースに基づいており、理解しやすいように分類されています。

**Common Weakness Enumeration（CWE）**は、ハードウェアとソフトウェアの弱点や脆弱性を分類する仕組みです。
アプリケーションのソースコードに含まれるセキュリティ問題を説明し、分類するために使用します。
CWE について詳しくは、Wikipedia の「[Common Weakness Enumeration](https://en.wikipedia.org/wiki/Common_Weakness_Enumeration)」を参照してください。

### ⌨️ やること: 既存のアラートを表示する

1. 上部のナビゲーションで **Security and quality** タブを選びます。

1. 左側のナビゲーションで **Findings** の領域を探し、**Code scanning** を選びます。
   - アラートがないことを確認します。脆弱性を含む pull request のコードはまだマージされていないため、想定どおりの結果です。

1. 作成した pull request に戻ります。失敗したチェックは無視し、**Merge pull request** ボタンをクリックします。

   <img width="300" alt="Merge pull request ボタン" src="../images/merge-button.png" />

1. **Delete branch** をクリックします。マージ後のブランチは不要です。

1. CodeQL が `main` ブランチへの新しい変更を分析するまで、少し待ちます。

1. **Security and quality** タブに戻ります。

1. 左側のナビゲーションで、**Code Scanning** の横に `1` と表示されていることを確認します。未対応のアラートが 1 件あることを示しています。

   <img width="250" alt="コードスキャンアラートの件数" src="../images/code-scanning-alerts-count.png" />

### ⌨️ やること: アラートを確認する

1. 左側のナビゲーションで **Code scanning** を選びます。

1. 未対応のアラートをクリックします。

1. 概要、脆弱性の説明、推奨される解決策を確認します。

   <img width="600" alt="アラートの概要" src="../images/alert-overview.png" />

1. 監査証跡に脆弱性の発生元が記録され、pull request から取り込まれたことが示されている点を確認します。

### ⌨️ やること: アラートを却下して再度開く

1. 右上にある **Dismiss alert** ドロップダウンをクリックします。

1. `Used in tests` を選び、次の説明を入力します。

   ```md
   This is a playground repository for learning about CodeQL alerts.
   ```

   <img width="300" alt="アラートを却下する選択肢" src="../images/dismiss-alert-options.png" />

1. **Dismiss** ボタンをクリックします。
   - アラートの状態が `Dismissed` に変わります。
   - アラートを閉じた人と入力した説明を示す読み取り専用の項目が、監査証跡に追加されます。

   <img width="300" alt="アラートの却下を示す監査ログの項目" src="../images/audit-log-alert-dismissed.png" />

1. 右上にある **Reopen alert** ボタンをクリックします。
   - アラートの状態が `Open` に戻ります。
   - アラートを開いた人を示す読み取り専用の項目が、監査証跡に追加されます。

1. アラートを閉じて再度開いたら、次のコメントを Issue に追加し、Mona に作業の確認と次の Step の投稿を依頼します。

   ```md
   Hey @professortocat, I've closed an reopened an alert. What is the next step?
   ```
