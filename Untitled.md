
#システム変更作業手順書

## 写トル用検証バケット設定変更・試験
### 事前準備

AWSマネジメントコンソールへログインする

> https://haseko.signin.aws.amazon.com/console へアクセスする
> TIS-TMP-PU-01でAWSマネジメントコンソールへログインする

TIS-PU-01に権限をつける

* TIS-TMP-PowerUsersグループのインラインポリシー「Policy-S3-TIS-PowerUsers」を更新する
* Policy-S3-TIS-PowerUsersではなくTEMP PUのPolicy-S3-TIS-PowerUsers

>[Identity and Access Management]-[グループ]クリック
>[TIS-TMP-PowerUsers-2]クリック
>アクセス許可タブにて以下ポリシーの[ポリシーの編集]クリック
>Policy-S3-TIS-PowerUsers
>前手順と同様にポリシーを追記し[ポリシーの検証]、[ポリシーの適用]クリック

### バケットポリシー変更
バケットポリシー変更

* 写トル検証用バケットを作成する
>[s3]クリック
>バケット一覧にて「hct-syatoru-test-bucket」選択
>[アクセス許可]-[バケットポリシーの編集]選択
>バケットポリシーエディターにて『AWS詳細設計書「5. S3設計(表：建設写トル検証バケット)」』を参照し、バケットポリシーを編集し[保存]クリック

### 試験

正常系試験(事前準備[アクセスキー設定])
* 運用端末(アクセス許可されたグローバルIPアドレスを使用する端末)へアクセスキーを登録する

>運用端末にてコマンドプロンプトを開く
>以下コマンドを入力する


```html:sample
aws configure
AWS Access Key ID
＜HCT-AC-TEST-01のアクセスキー＞
AWS Secret Access Key
＜HCT-AC-TEST-01のシークレットアクセスキー＞
Default region name
ap-northeast-1
Default output format
json
```

正常系試験(許可されたIP：ファイルアップロード)
