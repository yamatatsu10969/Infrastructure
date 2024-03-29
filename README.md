# Infrastructure
about infrastructure 


## 講義

# 基礎から

ネットワークはイーサネット

## ネットワークの基礎

ネットワークは特定の相手へデータを送りたい

### 物理的な機器（L1）

- UTPケーブル
- 光ファイバ
- スイッチングハブ

### 物理的な通信(L2)

MACアドレスなど。

物理的な機器に振られる番号→例えばこのPCにもMACアドレスが振られている。

### IPアドレス（L3）

MACアドレスとIPアドレスの違いは、

MACアドレスは、地図上の緯度経度みたいなもん。

IPアドレスは住所

ポートは受取人

## ポート

ポートの役割は、そこでアプリケーションが待ち構えている。

アプリケーションを識別する番号。決められた番号のポートでアプリケーションが待ち受ける！

80番はwebアプリに使われる。

- TCP
- 

    通信するためのルールと思えばいいです
    L1は接続するための機械の取り決めです。LANケーブルなのか無線なのか
    L2はMACアドレスという決まり等で通信する取り決め
    L3はIPアドレスで通信する決まり
    

    MACアドレスは、地図上の緯度経度みたいなもん。
    IPアドレスは住所
    ポートは受取人

### パケットとは

データ送信の最小単位

## OSI参照モデル

[](https://www.notion.so/b9bf09baaa694412afe2b34105221162#4897b414d4c04422b277d3feff9ed519)

[](https://www.notion.so/b9bf09baaa694412afe2b34105221162#32b8527d085c4c76b67a468b5c0b8843)

## グローバルIPアドレスとプライベートIPアドレス

127.0.0.1 は自分自身を表すIPアドレス

ローカルホストと一緒。

[localhost:8080](http://localhost:8080) と一緒っすね。

サブネット

デフォルトゲートウェイ

### 送信の仕組み

宛先を指定して送ることができない。

効率化させる仕組みはあるけどね。

### ポート（代表的な）

- 80 webサーバ
- 25 メールサーバ
- 3306 mysqlサーバ
- 9999 ×
- 8080 webサーバ

### ポート　アプリ

- 22 SSH
- 25 SMTP
- 53 DNS
- 80 web(HTTP)
- 443 web(HTTPS)
- 3306 mysql

### メールを telnet のコマンドで送信できる

# ドメイン

DNSとは、ドメインネームサーバー

PC → www.yahoo.co.jpのIPアドレスを教えて。

サーバ（AWS） は, 182.22.25.124だよ！

    nslookup www.yahoo.co.jp
    ↑↑↑↑はadressを調べるコマンド。
    
    Server:		192.168.100.1
    Address:	192.168.100.1#53
    
    Non-authoritative answer:
    www.yahoo.co.jp	canonical name = edge12.g.yimg.jp.
    Name:	edge12.g.yimg.jp
    Address: 182.22.25.124

ネットワークに繋がった瞬間に、DNSサーバーもパソコンに設定される。

自分でも指定できるんだよ。

### hostsファイルのありか

    hostsを設定
    hostsファイルを編集
    
    sudo vi /private/etc/hosts

## レジストリ

    レジストリは、各ドメイン情報を持つデータベースを管理している機関です。ドメインによってレジストリは異なり、例えば「.com/.net」は、VeriSignによって管理されています。すべてのレジストラに対し平等にSRS（※1）へのアクセスを保証し、中立の立場である事が要求されています。

## レジストラ

    ICANN（※2）に認定されているレジストラは、直接レジストリと契約を結び、非営利団体ICANNのレジストラ認定方針（Registrar Accreditation Policy）とレジストラ認定規約（Registrar Accreditation Agreements)に基づき、十分な資源と意欲、技術、ビジネス能力を持っているドメイン登録業者です。 レジストラは、各レジストリとレジストリ・レジストラ契約（Registry-Registrar Agreement）を結び、SRSを使用してレジストリデータベースに直接ドメイン情報を登録する事が できます。

Route53

- クライアントサーバモデル
- P2Pモデル
    - ビットコイン
    - WebRTC
    - Winny(懐かしい)

## HTTP

Hypertext Transfer Protocol

データのやりとりのルール。

ハイパーテキストのルールだよ。

## Webサーバ

ユーザからデータを要求。

ルールはHTTPで行っている！

- Apache　アパッチ
- nginx エンジンエックス

## HTTPステータスコード

    100番台 案内（インフォメーション）
    200番台 正常処理 成功！！！
    300番台 移転通知 リダイレクト処理
    400番台 （クライアントにおける）処理失敗
    				401 認証エラー
    				403 アクセス権がないとき
    				404 そのページないよ〜
    500番台 サーバーエラー
    				500 構文エラーとか色々。

### 暗号化・復号化

暗号化して、復号化をする！

双方向に、変換が可能。

### ハッシュ

これは一方向！

ファイルが改竄されていないかをハッシュ値が異なるかどうかで調べることができる。

## 共通鍵・公開鍵・

### 共通鍵暗号方式

共通鍵で、暗号化して、

共通鍵で、復号化する。

### 公開鍵暗号方式

公開鍵で暗号化して、

秘密鍵で復号化する！

逆もある。

## SSL（Secure Sockets Layer）

暗号化して、通信している。

セキュア通信するための決まり。

TLSはSSLが元になっているけれど、SSLという名称が普及してしまっている。

（通信したい相手の）公開鍵を受け取って、それを使って、暗号化する。

そして、その暗号化したファイルを送って、相手は秘密鍵を使って、復号化できる

SSLサーバ証明書がなくても暗号化は可能

公開鍵暗号方式で共通鍵を渡す。

ショッピングサイト

公開鍵秘密鍵では時間がかかる。計算量が膨大

一番最初だけ、公開鍵暗号方式(公開鍵秘密鍵)で通信して、そのあとは、共通鍵暗号方式で通信している。

### SSLサーバ証明書

- 電子署名を使って、第三者に存在を証明してもらう仕組み
- 自分で自分の証明はできない
- 第三者はOSやブラウザに仕込まれている
    - 信用する要因は、OSやブラウザのみ。自分では証明できないので、OSかブラウザ（Amazonやマイクロソフト、Apple）を使ったサービスやハードを証明にしている。
- AWSだとELBやCloudFrontで無料

## Linuxとは

OSの一種　MacやWindowsと一緒

## カーネルとは

基本的な交通整理をしている！！！

- ハードウェアを直接制御する部分
- CPUやメモリをアプリに割り当てたり
- マウスなんかの周辺機器を制御したり
- ファイルを読み書きしたり
- アプリケーションの実行単位（プロセス）を管理したり

## Linuxコマンド

リモートデスクトップで、コマンドじゃなくて、GUIでもできるけど、メモリの無駄遣い

→ コマンドでメモリを無駄遣いせず頑張りましょう。

`ls -l`

    drwxr-xr-x@  8 yamamototatsuya  staff      256 May 25 16:08 Oshidori_12.9_gen_2nd
    drwxr-xr-x@  7 yamamototatsuya  staff      224 May 25 16:08 Oshidori_12.9_gen_3rd
    drwxr-xr-x@  8 yamamototatsuya  staff      256 May 25 16:11 Oshidori_5.5inc_7Plus
    drwxr-xr-x@  8 yamamototatsuya  staff      256 May 25 16:12 Oshidori_6.5inc_XS_Max
    drwxr-xr-x  10 yamamototatsuya  staff      320 May 28 09:46 additional func
    drwxr-xr-x  85 yamamototatsuya  staff     2720 Jul 11 19:37 vector image
    -rw-r--r--   1 yamamototatsuya  staff  1031143 Jul 11 19:39 vector image.zip
    r read
    w write
    x run

## `chmod`　を覚えるぞ。

chmod 444 は読み込み

chmod 500 読み込みと実行の権限

chmod 600 は自分だけの読み書き

chmod 700 は全ての権限

`chmod` は覚えておかなきゃ！

[サーバー・インフラ・premire！](https://www.notion.so/b9bf09baaa694412afe2b34105221162)

[https://www.notion.so/yamatatsutech/premire-b9bf09baaa694412afe2b34105221162#aedb68985f7d499c80b075535be04ccd](https://www.notion.so/yamatatsutech/premire-b9bf09baaa694412afe2b34105221162#aedb68985f7d499c80b075535be04ccd)

# SSH

    SSHとは、Secure Shell（セキュアシェル）の略称で、リモートコンピュータと通信するためのプロトコルです。
    認証部分を含めネットワーク上の通信がすべて暗号化されるため、安全に通信することができます。

SSH は 22番ポートを使っているぞ。

# クラウドサービスとは

とりあえずインターネットに繋がっていればやりたいことができる

インターネットのどこかで行われているサービス

### PaaS Platform as a Service

- AWS RDS
- AWS S3
- Heroku
- Azuru ?

### SaaS Software as a Service

- gmail
- dropbox

### IaaS Infrastructure as a Service

- AWS

# AWS（Amazon Web Service）

### サービスは100個以上あるらしい。

## リージョンとアベイラビリティゾーン

- リージョン

    近いところを選ぶと早くなりそう。

- アベイラビリティーゾーン

    複数のデータセンターの塊。

    - アベイラビリティとは、システムを正常な状態で継続的に使い続けることができる耐久性のことである。

## EC2

- 仮想サーバーを立てることができるサービス
- 安い
- シェアしてるから安いよ〜
- すぐに使えるから良いよね。
- 物理的にメンテナンスしなくていい。

### 仮想化

- Macの上で Windows使ったりできる。
- ソフトウェアを使ってできる。
- VWで使えるよ〜。

### ホストOS型・ハイパーバイザー型

- ホストOS を介さないのが、ハイパーバイザー型

### docker は仮想化の環境を作るものじゃない

- コンテナは、昔からある技術
- Linux のリソースを使っている。

### なぜ仮想化するのか

- 共有して使いたい人が使いたいときに使う。
- 1台を分割して使う
- 共有して使うため。

## EC2のインスタンスを作成する

- 何もわからんのなら、Amazon Linuxのインスタンスを作成する↓↓↓↓↓↓↓↓↓
- Amazon Linux 2 AMI (HVM), SSD Volume Type - ami-0c3fd0f5d33134a76
- テナンシーで専用をすると、料金がバクあがりする
- T2/T3 はポイントが溜まっていく仕組み

### セキュリティグループ

- セキュリティグループが決まっていないと、アクセスができなくなる。
- ソースがマイIPだと、そのIPアドレスからしか入れなくなる。
- 

### ファイアオールとは

- ポートごとに、通す、通さないを制御する
- アクセスに対して許可を出すのが、ファイアオール

`open .` で現在地を開くことができるよ！

なるほどな〜

## S3

データを保存しておける場所

## RDB リレーショナルデータベース

使ってるよん。

バックアップもしてるよ！ 

## Multi-AZ


# コマンド一覧

```
​​cd
​​mkdir .ssh
​​chmod 700 .ssh
​​cd .ssh
​​mv ~/Desktop/test99.pem ./
​​chmod 600 test99.pem
​​ssh -i test99.pem ec2-user@xxxxxxxxxxx
​​
​​sudo su -
​​amazon-linux-extras install php7.3
​​yum install httpd php7.3
​​systemctl start httpd
​​
​​cd /var/www/html
​​vim index.html
​​
​​yum -y install php-devel php-pdo php-mbstring php-mcrypt php-mysqlnd php-xml php-gd php-opcache php-pecl-zip
​​
​​curl -sS https://getcomposer.org/installer | php
​​mv composer.phar /usr/local/bin/composer
​​composer config -g repos.packagist composer https://packagist.jp
​​composer global require hirak/prestissimo
​​
​​composer create-project --prefer-dist "laravel/laravel=5.5.*" ./app
​​
​​vim /etc/httpd/conf/httpd.conf
​​systemctl restart httpd
​​chown -R apache:apache app
​​
​​php artisan make:auth
​​php artisan migrate
​​
​​yum install docker
​​systemctl start docker
​​
​​docker pull mysql:5.7
​​docker run --name mysql -e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=test -e MYSQL_USER=test -e MYSQL_PASSWORD=testtest -p 3306:3306 -d mysql:5.7
​​
​​DB_CONNECTION=mysql
​​DB_HOST=127.0.0.1
​​DB_PORT=3306
​​DB_DATABASE=test
​​DB_USERNAME=test
​​DB_PASSWORD=testtest
​​
​​php artisan migrate
```
