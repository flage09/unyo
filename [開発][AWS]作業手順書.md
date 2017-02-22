

#システム変更作業手順書
| 作業予定日| 作業開始時間   | T社担当者                       | 顧客担当者|
| --------------- |:---------------:| -------------------- | -------:|
| 2017/1/10（月） | 11:00～13:00    |K                       |N       |


## 検証バケット設定変更・試験
### 事前準備

- [ ]　AWSマネジメントコンソールへログインする

> https://h.signin.aws.amazon.com/console へアクセスする
> TMP-PU-01でAWSマネジメントコンソールへログインします。
- [ ]　PU-01に権限をつける
- [ ]　PU-02に権限をつける
- [ ]　PU-04に権限をつける

* TMP-PowerUsersグループのインラインポリシー「Policy-S3-PowerUsers」を更新する
* Policy-S3-PowerUsersではなくTEMP PUのPolicy-S3-PowerUsers

![Qiita](http://blog.tyotto.co.jp/wp-content/uploads/2016/04/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2016-04-02-12.34.13-644x475.png)

>[Identity and Access Management]-[グループ]クリック
>[TMP-PowerUsers-2]クリック
>アクセス許可タブにて以下ポリシーの[ポリシーの編集]クリック
>Policy-S3-PowerUsers
>前手順と同様にポリシーを追記し[ポリシーの検証]、[ポリシーの適用]クリック

### バケットポリシー変更
- [ ]　バケットポリシー変更

* 検証用バケットを作成します。
>[s3]クリック
>バケット一覧にて「s-test-bucket」選択
>[アクセス許可]-[バケットポリシーの編集]選択
>バケットポリシーエディターにて『AWS詳細設計書「5. S3設計(表：検証バケット)」』を参照し、バケットポリシーを編集し[保存]クリック

### 試験

- [ ]　正常系試験(事前準備[アクセスキー設定])
* 運用端末(アクセス許可されたグローバルIPアドレスを使用する端末)へアクセスキーを登録する

>運用端末にてコマンドプロンプトを開く
>以下コマンドを入力する

AAAAAAAAAAAAAAAAAA
AAAAAAAAAAAAAAAAAA

```html:sample
aws configure
AWS Access Key ID
＜AC-TEST-01のアクセスキー＞
AWS Secret Access Key
＜AC-TEST-01のシークレットアクセスキー＞
Default region name
ap-northeast-1
Default output format
json
```

