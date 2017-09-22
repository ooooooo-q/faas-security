# faas-security

FaaS のセキュリティ 

この資料は [【NDSiN#12×Niigata.js×C4N】JavaScript 2017春](https://nds-meetup.connpass.com/event/54362/) の発表資料(予定）です。

検証が十分でない記述が含まれます。

### FaaS is ?

(要調査)
- リクエストの度に生成される
- ステートレス
- 時間単位での課金


### FaaS 

- AWS Lambda
- Google Cloud Functions
- Microsoft Azure Functions、
- [OpenFaaS](https://www.openfaas.com)
- IBM OpenWhisk
- Iron.io
- Webtask


### serverless framework

- Serverless Framework
- apex

### 経緯

- AWS LambdaでPoCが発表されてからパッチが適用されるまでの話
- Cloud Functions sampleでの脆弱性

=> FaaSでのセキュリティはどう担保されているのか

#### AWS Lambdaでの話

- ghostscript の脆弱性として CVE-2016-7977 が昨年9月~10月ぐらいに情報がでていた
- REHL系ではImageMagick と一緒にghostscriptが入ってしまい、Lambdaが動くAmazon LinuxはREHL系（要確認）なので影響を受けていた
- 細工した画像をアップロードされると、サーバのファイルの中身が取得できる状態だった
- 連絡したら、その数日後に修正がでた（おそらく偶然）

ミドルウエアの脆弱性によるものは利用者とサービス提供者、どちらの負担になる？

### Cloud Functions sample

- Imagemagickを呼び出すところで、ファイル名にevilなものがあると任意のshellが実行
- sampleとしてあまりよくない


### 共有責任モデル



### セキュリティのチェック点(要検討)

- コードレベル
- ミドルウエア
- 権限まわり
- 影響範囲
- ログ

### 12 factor apps

### FaaSの用途

- サムネイル生成
- 他のサービスとの連携
- job schedule

### サービスによる違い

- サービス連携


### サービスそのもののセキュリティ

- 2FA?

### ImageMagick

- policy.xmlを追加すれば防げる？
- 他のサービスに入ってる？
- [With OpenFaaS](https://blog.alexellis.io/serverless-imagemagick/)


