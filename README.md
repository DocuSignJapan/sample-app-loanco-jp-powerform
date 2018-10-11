
### DocuSign PowerForm サンプル(Webフォームとの連携)

[LoanCoサンプル](https://github.com/DocuSignJapan/sample-app-loanco-jp-nodejs)の個人ローン申込書Webフォームで入力された内容を、DocuSignのPowerFormに引き渡し、そのままDocuSignエンベロープに内容を再入力することなく、署名して申込を行うサンプルです。
実際に動作するデモは、下記からアクセスできます。
https://docusignjapan-samplewebformdemo01.netlify.com/

#### 自分の環境で動作させる場合

1. [Free Developer Sandbox](https://go.docusign.com/o/sandbox/)を作成

2. GitHubレポジトリからクローン
```
    git clone <repo url> 
    cd <repo directory>
```
3. DocuSignサンドボックス環境にログインし、テンプレートをインポート
    ログイン後、テンプレートタブをクリックし、新規ボタンを押し、「テンプレートのアップロード」を選択します。
    /templateフォルダにある、個人ローン(PowerForm).jsonをアップロードしてください。

4. インポートされたテンプレートに、PowerFormを作成
    テンプレートをクリックし、その他 > PowerFormを作成、を選択し、「作成」ボタンを押します。

5. PowerForm URLをindex.htmlに反映
    クローンしたフォルダの直下にある、index.htmlの105行目のformタグにある、action属性内のURLを4の手順で取得したURLに変更し保存します。

6. ブラウザで、index.htmlを開く


##### 注意点
FormからDocuSignのPowerFormにPOSTする場合で、日本語がフォーム内容に含まれる場合は、UTF-8でエンコードされている必要があります。
サンプルではない実際のWebフォームがShift JISなどで生成されている場合は、accept-charset='UTF-8'をFormの属性につけるか、onclick="document.charset='UTF-8';"などを追記してください。


#### ライセンス 

The DocuSign LoanCo Sample App is licensed under the MIT [License](LICENSE).


