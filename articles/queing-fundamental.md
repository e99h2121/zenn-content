---
title: "キューイングシステム色々" # 記事のタイトル
emoji: "🕘" # アイキャッチとして使われる絵文字（1文字だけ）
type: "tech" # tech: 技術記事 / idea: アイデア記事
topics: ["初心者", "Queue"] # タグ。["markdown", "rust", "aws"]のように指定する
published: true # 公開設定（falseにすると下書き）
---


[キューイングシステムとは](https://udemyfun.com/python-queueing-system/)
[メッセージキューイング（MQ）とは - 意味をわかりやすく - IT用語辞典 e-Words](https://e-words.jp/w/%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%AD%E3%83%A5%E3%83%BC%E3%82%A4%E3%83%B3%E3%82%B0.html)

> メッセージキューはその名の通りキュー（queue/待ち行列）構造となっており、複数のメッセージを預かる場合は先に書き込まれた方から順に読み出すFIFO（First-In First-Out：先入れ先出し）方式でメッセージを送り出す。受け渡しが完了したメッセージは消去され、次のメッセージの送受信に備える。


> ブローカー、いわゆる仲介ですが、ブローカーなしのキューイングシステムとブローカーありのキューイングシステムがあり、ブローカーなしの場合、リクエストがあったらすぐにリクエストに答えるのに対し、ブローカーありは、タスクを受けて、バックグラウンドでサーバーに処理をスケジュールして、スケジュールに応じた処理を返すという感じです。

> ブローカーなしだとすぐにレスポンスを返せるのですが、タスクが保存されていないので、何かあった場合は処理が完結しないのに対して、ブローカーありは処理に時間がかかるものの、タスクが保存されているので、何かあってもその処理を最後まで実行できます。

[メッセージキュー - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%AD%E3%83%A5%E3%83%BC)
[ZOZOTOWN カート投入の分散キューイングシステム 〜 プロダクションレディまでの歩み - ZOZO TECH BLOG](https://techblog.zozo.com/entry/production-ready-zozotown-cart-queueing-system)
[Amazon SQS（サーバーレスアプリのためのメッセージキューサービス）| AWS](https://aws.amazon.com/jp/sqs/)
[Amazon Kinesis Data Streams（リアルタイム分析向け大規模データを収集）| AWS](https://aws.amazon.com/jp/kinesis/data-streams/)
[Queue Storage | Microsoft Azure](https://azure.microsoft.com/ja-jp/services/storage/queues/)
[Event Hubs - リアルタイムのデータ インジェスト | Microsoft Azure](https://azure.microsoft.com/ja-jp/services/event-hubs/)

https://www.slideshare.net/masaakikoishikawa/techdojoaboutmq001pptx

## 色々
- Kafka
    - https://kafka.apache.org/
    - [Apache Kafka 入門 - Qiita](https://qiita.com/keikesu0122/items/48be51a65d34d90c11e9)
- Rabbitmq
    - https://www.rabbitmq.com/
- Celeryq
    - https://docs.celeryq.dev/en/stable/
- Nsq
    - https://nsq.io/

