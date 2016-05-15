# gce compute engine 準備 手順

## [apcom アカウント](http://wmail.ap-com.co.jp/)でgoogleにログイン
## [google cloud Platform](https://console.cloud.google.com/home/dashboard?project=apc0001-1302) にアクセス
- 自分のアカウントでログインできていることを確認刷する。
- APC0001 (project id: apc0001-1302) が選択されていることを確認する。
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
