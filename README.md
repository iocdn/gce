# gce compute engine 準備 手順

## SSH鍵の生成
- Windowsの場合
 - TeraTerm を開く
 - 新しい接続をキャンセル
 - 設定 > SSH鍵生成
 - 鍵の種類をRSA,ビット数を 2048にして、生成ボタンをクリック
 - 公開鍵の保存と秘密鍵の保存をクリックして　公開鍵(id_rsa.pub) と秘密鍵(id_rsa)を保存

- Macの場合
 - ssh-keygen -t rsa コマンドで公開鍵/秘密鍵を生成してください。

## compute engine の作成
1. [apcom アカウント](http://wmail.ap-com.co.jp/)でgoogleにログイン

2. [google cloud Platform](https://console.cloud.google.com/home/dashboard?project=apc0001-1302) にアクセス
 - 自分のアカウントでログインできていることを確認してください。
 - APC0001 (project id: apc0001-1302) が選択されていることを確認してください。
![image](/images/chef-logo.png?raw=true =10x20 "Optional Title")

## ツールとサービスから　[Compute Engine](https://console.cloud.google.com/compute/instances?project=apc0001-1302)を選択
## [VMインスタンス > インスタンスを作成](https://console.cloud.google.com/compute/instancesAdd?project=apc0001-1302)

名前 iocdn-apc0001
ブートディスク centos
ファイアウォール http/https トラフィックを許可する
管理、ディスク、ネットワーキング、SSH キー　を展開
SSHキータブを選択
SSH公開鍵を貼り付け
作成


公開鍵と秘密鍵を事前に配っておく

## SSHでログイン

(https://raw.githubusercontent.com/iocdn/gce/chef_short_cource01/images/chef-logo.png)

![image](/images/chef-logo.png?raw=true =10x20 "Optional Title")


<img src="/images/chef-logo.png?raw" alt="Drawing" style="width: 50px;"/>
