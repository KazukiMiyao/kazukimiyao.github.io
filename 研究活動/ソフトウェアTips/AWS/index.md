---
layout: default
title: AWS
---

* AWSに関するメモをつらつら書きます [#e05260a7]

** 東野研 Console URL [#u68218f6]
- https://higashi-lab.signin.aws.amazon.com/console
- アカウントはすでにAWSアカウントを使っている人に作ってもらう．

** 命名規則 [#u46f6b64]
インスタンス名，セキュリティグループ名，バケット名などは接頭辞に作成したユーザ名を付けるようにしてください．~
例: yuma-ymd-in-room

** IPアドレス [#l8c125be]
2017/10/2 AWS Elastic IPの上限を5->15に引き上げ
足りなくなったら再度上限数引き上げの申請をしますが，
どこまで増やしてもらえるかわからないので，
IPの無駄遣いはお控えください．

** EC2インスタンス起動時に自動でDNS設定を行う [#ue8db19c]
Elastic IPを使わずにDNS解決をしたい時に利用 ~
http://qiita.com/romba/items/9486ef97ea8891029245
