# AWSについて

## AWSの主要サービス
- EC2 (Amazon Elastic Compute Cloud)
- Route 53 (Amazon Route 53)
- S3 (Amazon Simple Storage Service)
- Cloud Front (Amazon Cloud Front) : コンテンツキャッシュ
- RDS (Amazon Relational Database Service)
- ELB (Elastic Load Balancing)

静的ページであれば、S3に配置することで
多くのアクセスに耐えられる。

### 最近の変化(2015/2)
 - EC2の性能向上、高性能T2インスタンス
 - SSDサポート
 - VPC提供
 - UI変更(一部のコマンド専用操作がWeb操作化)

## EC2

 - 11のリージョン、リージョン内の複数のアベイラビリティゾーン(AZ)。
異なるAZを使うことで災害対策。
 - リージョンによって価格が違う。東京とオレゴン。
レイテンシーと価格の兼ね合い。
 - 複数のEC2インスタンスを使う場合は、異なるAZに配置する。
AZ間は、専用線で接続。

### Scale Upパターン
 - インスタンス生成後に、CPUやメモリを変更。(一時停止は必要)

### EBS (Elastic Block Store)
 - EC2のストレージとして使われる。追加も可能。
 - EBSを使わずにEC2内のローカルインスタンスストアを使うことも可能。
S3からマシンイメージを読み込む。Storebacedと呼ばれる手法
 - EBSはスナップショット保存が可能で、バックアップが容易。
ディスク容量変更も可能(Ondemand Diskパターン)
 - ギガバイト単位の課金。作成時点から課金対象。

### AMI (Amazon Machine Image)
- マシンイメージ
- Amazon Linux, RHEL, Ubuntu Server, Windows Server 2008/2012

### IPアドレス
- EC2は、VPC(Virtual Private Cloud)に設置される。
- VPCはユーザ毎に分離。
- デフォルトVPC : `172.31.0.0/16`

2種類のIPアドレス

1. Private DNS, Private IPs
  - `ip-XXX-XXX-XXX-XXX.ap-northeast-1.compute.internal` (`XXX`=IPアドレス)
  - 破棄するまで同じIPアドレス
 2. Public DNS, Public IPs
  - `ec2-XXX-XXX-XXX-XXX.ap-northeast-1.compute.amazonaws.com`
  - 起動するたびに別のIPアドレス
  - Elastic IP Address を使うと固定化

### 操作
- Start
- Stop
- Reboot
- Terminate(終了)
 - Terminate Protection

## 参考文献
- 「Amazon Web Services クラウドデザインパターン 実装ガイド 改訂版」
