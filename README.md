# gce compute engine 準備

## SSHの鍵の作成

### 1台目の仮想マシン(__apc-社員番号__)ログイン用 SSH鍵作成

- Windowsの場合
 - TeraTerm を開く
 - 新しい接続をキャンセル
 - 設定 > SSH鍵生成
 - 鍵の種類をRSA,ビット数を 2048にして、生成ボタンをクリック
 - 公開鍵の保存と秘密鍵の保存をクリックして　公開鍵(id_rsa.pub) と秘密鍵(id_rsa)を保存

- Macの場合
 - ssh-keygen -t rsa コマンドで公開鍵/秘密鍵を生成してください。

### 2台目の仮想マシン(__apc-社員番号2__ )ログイン用 SSH 鍵生成

 - __本作業は、1台目の仮想マシン作成後、2台目の仮想マシンを作成する際に実施してください。__
  - 1台目の仮想マシンにログインできましたら、1台目の仮想マシン以下の手順でSSH鍵を作成してください。
  - 作成したSSH鍵の公開鍵は, 2台目の仮想マシン作成時、 __SSHキー登録__ で登録してください。
 
```bash
 $ ssh-keygen -t rsa -P ''
  Enter file in which to save the key (/アカウント名/.ssh/id_rsa): そのまま[ENTER]
  
 $ cat ~/.ssh/id_rsa.pub
 = 以下に表示される内容をコピーして登録してください =
```

## 仮想マシン(以下VM) の作成
1. [apcアカウント](http://wmail.ap-com.co.jp/)でgoogleにログイン

2. [google cloud Platform](https://console.cloud.google.com/home/dashboard) にアクセス
 - 自分のアカウントでログインできていることを確認してください。
 - APC0001 or APC0002 or APC0003 (project id: apc000[123]-1302) が選択されていることを確認してください。
 
3. ツールとサービスから　[Compute Engine](https://console.cloud.google.com/compute/instances?project=apc0001-1302)を選択
4. [VMインスタンス > インスタンスを作成](https://console.cloud.google.com/compute/instancesAdd?project=apc0001-1302)でインスタンスを作成していきます。

 | 項目        | 値          |備考|
 |:--------------:|:-------------------------------:|:-------:|
 |名前            |apc-社員番号(1台目) , apc-社員番号-2 (2台目) |インスタンス名|
 |ブートイメージ  |centos                           |OSイメージ          |
 |ファイアウォール|http/https トラフィックを許可する|                    |
 |SSH 公開鍵      |[SSH鍵の生成](#SSH鍵の生成)で作成した公開鍵|          |

  - インスタンス名の入力( インスタンス名は 1台目は __apc-社員番号__  , 2台目は  __apc-社員番号2__ としてください)
  
   ![image](/images/01_instance_name.png "インスタンス名")
  
  -  ブートイメージの選択
  
   ![image](/images/02_bootdisk.png "ブートイメージの選択")
  
   ![image](/images/03_bootdisk_select.png "ブートイメージの選択2")
   
  - ファイアウォールの設定
  
   ![image](/images/04_firewall.png "ファイアウォールの設定")
  
  - SSHキー登録
  
   ![image](/images/05_ssh1.png "SSHキー登録1")
  
   ![image](/images/06_ssh2.png "SSHキー登録2")
  
  - 作成
  
   ![image](/images/07_create.png "作成")
  
  - 外部IPの確認
  
   ![image](/images/08_create2.png "作成")
  
