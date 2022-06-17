---
title: "AWS SAA なぐり書き (4)" # 記事のタイトル
emoji: "📝" # アイキャッチとして使われる絵文字（1文字だけ）
type: "tech" # tech: 技術記事 / idea: アイデア記事
topics: ["初心者", "SAA"] # タグ。["markdown", "rust", "aws"]のように指定する
published: true # 公開設定（falseにすると下書き）
---

## EC2

- [インスタンスタイプ - Amazon EC2 | AWS](https://aws.amazon.com/jp/ec2/instance-types/)
- [Amazon EC2 の料金 | AWS 公式](https://aws.amazon.com/jp/ec2/pricing/)
    - Savings Plans
    - Dedicated Hosts
        - お客様専用の物理 EC2 サーバー

## CloudWatch, CloudTrail

- [Amazon CloudWatch Logs とは - Amazon CloudWatch Logs](https://docs.aws.amazon.com/ja_jp/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)
- [よくある質問 - AWS CloudTrail | AWS](https://aws.amazon.com/jp/cloudtrail/faqs/) 90日

## ストレージなど

- S3
	- [Amazon S3（拡張性と耐久性を兼ね揃えたクラウドストレージ）｜AWS](https://aws.amazon.com/jp/s3/)
	- 日付ベースの順次命名で処理を並列化し高速に
	- 比較
        - [Amazon S3 ストレージクラスを使用する - Amazon Simple Storage Service](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/storage-class-intro.html#sc-compare)
        - [6つのS3ストレージクラスの選択に迷った時みるチャートをつくってみた | DevelopersIO](https://dev.classmethod.jp/articles/should_i_choice_s3_storage_class/)
    - ライフサイクル管理
    - バージョニング機能
    - Webサイトホスティング
        - 独自ドメインしたい場合はCNAME
        - CloudFrontを前段に配置する場合はバケット名とドメイン名を合わせる必要はない
    - アクセス管理
        - バケットポリシー
        - ACL
        - IAM
        - 署名付きURL
    - Glacier
        - ボールトロック: [Amazon S3 Glacier ボールトロック - Amazon S3 Glacier](https://docs.aws.amazon.com/ja_jp/amazonglacier/latest/dev/vault-lock.html)
- EBS
	- [Amazon EBS（EC2 ブロックストレージボリューム）| AWS](https://aws.amazon.com/jp/ebs/)
	- 拡張はできるが縮小はできない
- EFS
- インスタンスストア
	- [Amazon EC2 インスタンスストア - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/InstanceStorage.html)
	- [EC2の揮発性ストレージ「インスタンスストア」を使ってみよう！ | DevelopersIO](https://dev.classmethod.jp/articles/howto-ec2-volatile-block-storage-instance-store/)
	- 汎用モード
	    - レイテンシーが最も低い
	- 最大I/Oモード
	    - 同時アクセス
- CloudFront
	- [Amazon CloudFront（グローバルなコンテンツ配信ネットワーク）| AWS](https://aws.amazon.com/jp/cloudfront/)
- ElastiCache
	- [Amazon ElastiCache（インメモリキャッシングシステム）| AWS](https://aws.amazon.com/jp/elasticache/)
	- ユーザー行動データの高速な処理には最適なDBであり、行動データ記録に応じたリアルタイムのランキング処理やアイテム出現などを実現
	- Radis用ElastiCache
		- シングルスレッドで排他的
	- Memcachd用ElastiCache
- Elasticsearch
	- [Elasticsearch とは何か? – アマゾン ウェブ サービス](https://aws.amazon.com/jp/opensearch-service/the-elk-stack/what-is-elasticsearch/)
- Amazon RDS
	- [Amazon RDS（マネージドリレーショナルデータベース）| AWS](https://aws.amazon.com/jp/rds/)
- Amazon Aurora
	- [Amazon Aurora（高性能マネージドリレーショナルデータベース）| AWS](https://aws.amazon.com/jp/rds/aurora/)
	- [Amazon Aurora Global Database | AWS](https://aws.amazon.com/jp/rds/aurora/global-database/)
		- クロスリージョンのディザスタリカバリ
- DynamoDB
	- [Amazon DynamoDB（マネージド NoSQL データベース）| AWS](https://aws.amazon.com/jp/dynamodb/)
		- デフォルトは結果整合性モデルだが、オプション機能で強い整合性モデルも利用
		- 利用負荷があらかじめ予測できる場合はプロビジョンドスループット
		- [Amazon DynamoDB Cross-region Replicationを試してみた | DevelopersIO](https://dev.classmethod.jp/articles/dynamodb-crossregion-replication/)
		- DynamoDB Accelerator(DAX) を有効化することで、DynamoDBテーブルはミリセカンドからマイクロセカンドへの最大 10 倍のパフォーマンス向上
		- DynamoDB Streamsは24時間
		- RCU/WCU
		- 結果整合性
- Amazon Redshift
	- [Amazon Redshift（高速、シンプル、費用対効果の高いデータウェアハウス）| AWS](https://aws.amazon.com/jp/redshift/)
- Amazon Neptune
	- [Amazon Neptune（完全マネージド型グラフデータベースサービス）| AWS](https://aws.amazon.com/jp/neptune/)
- Amazon DocumentDB
	- [Amazon DocumentDB（MongoDB 互換のドキュメントデータベース）| AWS](https://aws.amazon.com/jp/documentdb/)
- Amazon Keyspaces
	- [Apache Cassandra 用 Amazon Keyspaces – アマゾン ウェブ サービス](https://aws.amazon.com/jp/keyspaces/)
- Amazon Timestream
    - [Amazon Timestream（完全マネージド型の時系列データベース）| AWS](https://aws.amazon.com/jp/timestream/)
- Amazon QLDB
    - [Amazon QLDB（フルマネージド型台帳データベース）| AWS](https://aws.amazon.com/jp/qldb/)

## ルーティングなど

- [ルーティングポリシーの選択 - Amazon Route 53](https://docs.aws.amazon.com/ja_jp/Route53/latest/DeveloperGuide/routing-policy.html)
    - シンプルルーティングポリシー
    - フェイルオーバールーティングポリシー
        - アクティブ/パッシブフェイルオーバーを構成する場合に使用
    - 位置情報ルーティングポリシー
    - 地理的近接性ルーティングポリシー
    - レイテンシールーティングポリシー
    - 複数値回答ルーティングポリシー
    - 加重ルーティングポリシー 
- [AWS Global Accelerator（アプリケーションの可用性とパフォーマンスを向上）| AWS](https://aws.amazon.com/jp/global-accelerator/)

## 接続など

- [AWS VPN（オンプレミスネットワークへどこからでも安全に接続）| AWS](https://aws.amazon.com/jp/vpn/)
- [AWS Direct Connect（AWS への専用ネットワーク接続）| AWS](https://aws.amazon.com/jp/directconnect/)

## マイグレーションなど

- [AWS Application Discovery Service（オンプレミスの情報を検出して移行を効率化）| AWS](https://aws.amazon.com/jp/application-discovery/)
- [リフトアンドシフト - AWS Application Migration Service](https://aws.amazon.com/jp/application-migration-service/)
- [AWS Database Migration Service（最小限のダウンタイムでデータベースを移行）| AWS](https://aws.amazon.com/jp/dms/)
- VM Import/Export
- [AWS DataSync（シンプルかつ高速なオンラインデータ転送）| AWS](https://aws.amazon.com/jp/datasync/)


## プロビジョニングなど

- [AWS CloudFormation（テンプレートを使ったリソースのモデル化と管理）| AWS](https://aws.amazon.com/jp/cloudformation/)
- [AWS Elastic Beanstalk（ウェブアプリの実行と管理）| AWS](https://aws.amazon.com/jp/elasticbeanstalk/)
- [AWS OpsWorks（Chef や Puppet を使って運用を自動化する）| AWS](https://aws.amazon.com/jp/opsworks/)
- [AWS CodePipeline（継続的デリバリーを使用したソフトウェアのリリース）| AWS](https://aws.amazon.com/jp/codepipeline/)

## コンテナなど

- [Amazon ECR（Docker イメージの保存と取得）| AWS](https://aws.amazon.com/jp/ecr/)
- [Amazon ECS（Docker コンテナを実行および管理）| AWS](https://aws.amazon.com/jp/ecs/)
- [Amazon EKS（AWS でマネージド Kubernetes を実行）| AWS](https://aws.amazon.com/jp/eks/)

## 通知

- [Amazon SNS（サーバーレスアプリのための pub/sub メッセージングサービス）| AWS](https://aws.amazon.com/jp/sns/)
- [Amazon MQ（ActiveMQ 向けマネージド型メッセージブローカーサービス）| AWS](https://aws.amazon.com/jp/amazon-mq/?amazon-mq.sort-by=item.additionalFields.postDateTime&amazon-mq.sort-order=desc)

## 暗号化

- [AWS Key Management Service（マネージド型の暗号化キー作成と管理）| AWS](https://aws.amazon.com/jp/kms/)

## SSL/TLS 証明書

- [AWS Certificate Manager（SSL/TLS 証明書のプロビジョン、管理、およびデプロイ）| AWS](https://aws.amazon.com/jp/certificate-manager/)

## その他

- データの移動や変換を簡単に自動化: [AWS Data Pipeline（データの移動や変換を簡単に自動化）| AWS](https://aws.amazon.com/jp/datapipeline/)
- 動画とデータストリームをリアルタイムで容易に収集、処理、分析: [Amazon Kinesis（ストリーミングデータをリアルタイムで収集、処理、分析）| AWS](https://aws.amazon.com/jp/kinesis/)
    - [Amazon Kinesis Data Streams（リアルタイム分析向け大規模データを収集）| AWS](https://aws.amazon.com/jp/kinesis/data-streams/)
    - [Amazon Kinesis Data Firehose（ストリーミングデータをデータストアや分析ツールにロード）| AWS](https://aws.amazon.com/jp/kinesis/data-firehose/)
    - [Amazon Kinesis Data Analytics（ストリーミングデータをリアルタイムで処理）| AWS](https://aws.amazon.com/jp/kinesis/data-analytics/)
- STS: [IAM の一時的な認証情報 - AWS Identity and Access Management](https://docs.aws.amazon.com/ja_jp/IAM/latest/UserGuide/id_credentials_temp.html)
