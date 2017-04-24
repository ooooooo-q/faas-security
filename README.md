# faas-security

FaaS のセキュリティ 

この資料は [【NDSiN#12×Niigata.js×C4N】JavaScript 2017春](https://nds-meetup.connpass.com/event/54362/) の発表資料(予定）です。

検証が十分でない記述が含まれます。

### FaaS is ?

(要調査)


### FaaS 

- AWS Lam
- Google Cloud Functions
- Microsoft Azure Functions、
- IBM OpenWhisk
- Iron.io
- Webtask


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


### セキュリティのチェック点(要検討)

- コードレベル
- ミドルウエア
- 権限まわり
- 影響範囲

### サービスによる違い



