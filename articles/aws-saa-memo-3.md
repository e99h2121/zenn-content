---
title: "AWS SAA なぐり書き (3)" # 記事のタイトル
emoji: "📝" # アイキャッチとして使われる絵文字（1文字だけ）
type: "tech" # tech: 技術記事 / idea: アイデア記事
topics: ["初心者", "SAA"] # タグ。["markdown", "rust", "aws"]のように指定する
published: true # 公開設定（falseにすると下書き）
---

## [【2022年版】これだけでOK！ AWS 認定ソリューションアーキテクト – アソシエイト試験突破講座](https://www.udemy.com/course/aws-associate/)

- Well Architected Framework
    - Well-Architected Framework ホワイトペーパー
    - AWSのSAまたは認定パートナーによる支援制度
    - セルフチェック向けのWell-Architected Tool
- 6つの柱
    - Reliability
    - Performance Efficiency
    - Security
    - Cost Optimization
    - Operational Excellence
    - Sustainability
- AWS ベストプラクティス
    - スケーラビリティの確保
    - 環境の自動化
    - 使い捨てリソースの使用
    - コンポーネントの疎結合
    - サーバーではなくサービス（サーバレス）
    - 増大するデータ量対応
    - 単一障害点の排除
    - コスト最適化
    - キャッシュの利用
    - セキュリティの確保
    - 最適なデータベース選択

## 歴史
- [Amazon Simple Queue Service (SQS) – 15 年が経過した今もキューを実行中! | Amazon Web Services ブログ](https://aws.amazon.com/jp/blogs/news/amazon-sqs-15-years-and-still-queueing/)
- [歴史・年表でみるAWS全サービス一覧 －アナウンス日、General Availability(GA)、AWSサービス概要のまとめ－ - NRIネットコムBlog](https://tech.nri-net.com/entry/aws_history_and_chronology_all)

## [サンプル試験問題](https://d1.awsstatic.com/ja_JP/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate_Sample-Questions_v4.0_FINAL.pdf):

1. A
2. C  D: ロングポーリングでは、ReceiveMessage 要求に応答を送信する前に、メッセージが利用可能になるまで Amazon SQS の待機を許可することにより空の応答数を減少させることができます。
[SQS基礎まとめ](https://zenn.dev/hi_ka_ru/articles/a516af8bfc4457)
3. B
4. A, B: [AWS初心者-AWSネットワーク関連用語を基礎からおさらい｜コラム｜NURO Biz（ニューロ・ビズ）](https://biz.nuro.jp/column/aws-mama-031/)
5. B  C: インスタンスを休止状態にすると、RAM の内容が Amazon EBS ルートボリュームに保存されます。インスタンスが再起動すると、RAM の内容が再読み込みされます。
[Windows EC2インスタンスのハイバネーション(休止)を試してみた | DevelopersIO](https://dev.classmethod.jp/articles/ec2-windows-support-hibernation/)
6. C  D: セカンダリ ENI をインスタンスに追加できます。プライマリ ENI をインスタンスからデタッチすることはできませんが、セカンダリ ENI をデタッチして別のインスタンスにアタッチすることはできます。
[AWS ENI (Elastic Network Interface)について - Qiita](https://qiita.com/TaigoKuriyama/items/a1fcbadd10fa7ba41a04)
7. D  A: Web ブラウザは、Web ページとは異なるドメイン名を持つサーバーで作成されたスクリプトの実行をブロックします。Amazon S3 を CORS で設定して、スクリプトの実行を許可する HTTP ヘッダーを送信することができます。
8. D, E  C, D: 顧客提供キー (SSE-C) を使用してサーバー側の暗号化を行うことにより、Amazon S3 がPUT リクエストで提供される暗号化キーを使ってオブジェクトサーバー側を暗号化できます。オブジェクトを復号化するには、Amazon S3 の GET リクエストで同じキーを提供する必要があります。顧客には、データクライアントを Amazon S3 にアップロードしてダウンロード後に復号化する前に、データクライアント側を暗号化するオプションもあります。AWS SDK は、プロセスを合理化する S3 暗号化クライアントを提供します。
9. A
10. D  A: – スポットインスタンスは最もコストが低くて済むオプションですが、中断できないジョブや一定期間内に完了しなければならないジョブには適していません。オンデマンド インスタンスは、実行する秒数に応じて課金されます。
[料金 - Amazon EC2 スポットインスタンス - Amazon EC2 | AWS](https://aws.amazon.com/jp/ec2/spot/pricing/)

## メモ
- [【AWS資格】無料WEB問題集＆徹底解説 | ソリューションアーキテクト(SAA)](https://aws-exam.net/saa/saa_q_list.php?q_list=1)
- [AWS サービスがどこにあるのかまとめ - Qiita](https://qiita.com/saitotak/items/d2ede050e7a2224da46d)
- [プロビジョニングとは | クラウド・データセンター用語集／IDCフロンティア](https://www.idcf.jp/words/provisioning.html)
- [AWS: プロビジョニングサービス - Qiita](https://qiita.com/kakkie/items/6fb3ff85ae34bd965ffb)
    - Elastic Beanstalk
        - 定番構成の自動構築
    - OpsWorks
        - Chef環境を提供し、OSより上のレイヤーの自動構築をサポート
    - CloudFormation
        - JSONあるいは、YAMLのテンプレートを作成し、OSより下のレイヤーの自動構築をサポート
- [AWS再入門ブログリレー Amazon SQS編 | DevelopersIO](https://dev.classmethod.jp/articles/re-introduction-2020-amazon-sqs/)
- [AWS再入門ブログリレー2022 Amazon ECR編 | DevelopersIO](https://dev.classmethod.jp/articles/re-introduction-2022-ecr/)
- [AWS OpsWorks（Chef や Puppet を使って運用を自動化する）| AWS](https://aws.amazon.com/jp/opsworks/)
- [CloudWatch 標準メトリクス(監視項目) 一覧 - Qiita](https://qiita.com/gohatk@github/items/d1cfcbd1a3c1f7e6b4d3)
- [CloudWatchの標準メトリクスでEC2インスタンスのメモリ使用率はなぜ取得できないのか - Qiita](https://qiita.com/mittsukan/items/5185a119f9a22a0c88ff)
- [Amazon Route 53（スケーラブルなドメインネームシステム (DNS)）| AWS](https://aws.amazon.com/jp/route53/)
- [インスタンスストアと EBS の違いを教えてください。](https://aws.amazon.com/jp/premiumsupport/knowledge-center/instance-store-vs-ebs/)
- [EBS最適化インスタンスの効果を知るべくベンチマークを取ってみた | DevelopersIO](https://dev.classmethod.jp/articles/ebs-optimization-benchmark/)
- [Design for Failureの思想に見る、システム障害との向き合い方 | DATA INSIGHT | NTTデータ](https://www.nttdata.com/jp/ja/data-insight/2012/090601/)
- [EC2 拡張ネットワーキングとプレイスメントグループの効果を試す | DevelopersIO](https://dev.classmethod.jp/articles/ec2-placement-group/)
- [AWSとは？自社でクラウドを本格導入する時に困らない為の初心者向け早わかりガイド｜サービス｜法人のお客さま｜NTT東日本](https://business.ntt-east.co.jp/content/cloudsolution/column-259.html#section-05-01)
- [IOPS、スループット、レイテンシについて - Qiita](https://qiita.com/MAKOTO1995/items/21c9be9b7bc39fb4a702)
- [ファイル共有システムに出てくる用語（SAN,NAS,iSCSI,NFS,SMB,CIFSなど） - Qiita](https://qiita.com/zero_046/items/b596646695178316c6d6)
- [AWSの各サービスを雑に紹介する - Qiita](https://qiita.com/n-i-e/items/63f3f0ccb077bf8dc2f9)
- [AWSのSQSとSNSの違い - Qiita](https://qiita.com/miyuki_samitani/items/8d38c4421149d7469053)
- [Amazon S3 Transfer Acceleration を使用した高速かつ安全なファイル転送の設定 - Amazon Simple Storage Service](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/transfer-acceleration.html)
- [[初心者向け]Route53のトラフィックルーティングを実装する | DevelopersIO](https://dev.classmethod.jp/articles/implement-route53-routing-for-begineer/)
- [[初心者] EMRとは何ですか/とりあえずざっとまとめてチュートリアルしてみる | DevelopersIO](https://dev.classmethod.jp/articles/beginner-what-is-emr-overview/)
- [コンテナサービス「Amazon EKS」とは？実際に使用してみた｜コラム｜クラウドソリューション｜サービス｜法人のお客さま｜NTT東日本](https://business.ntt-east.co.jp/content/cloudsolution/column-try-40.html)
- [STSで一時クレデンシャルを発行する | DevelopersIO](https://dev.classmethod.jp/articles/sts-temporality-credential/)
- [初学者のためのAWS入門(3)-CloudFormation入門2 - Qiita](https://qiita.com/mshinoda88/items/65e7e145c7ec943af403#awsec2networkacl)
    - Egress 
        - サブネットからの送信トラフィックに適用される: true
        - サブネットへの受信トラフィックに適用される: false
        - 初期値は false 
- ゲートウェイ
    - [インターネットゲートウェイを使用してインターネットに接続する - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/ja_jp/vpc/latest/userguide/VPC_Internet_Gateway.html)
    - [パブリックサブネット vs プライベートサブネット | エクスチュア株式会社ブログ](https://ex-ture.com/blog/2021/07/14/publicsubnet-vs-plivatesubnet/)
    - [【AWS】NATゲートウェイとは、インターネットゲートウェイとの違い - Qiita](https://qiita.com/mzmz__02/items/2bf48c0645d41bc2fb69)
    - [2つのVPCエンドポイントの違いを知る | DevelopersIO](https://dev.classmethod.jp/articles/vpc-endpoint-gateway-type/)
- [AWS Global Accelerator（アプリケーションの可用性とパフォーマンスを向上）| AWS](https://aws.amazon.com/jp/global-accelerator/?blogs-global-accelerator.sort-by=item.additionalFields.createdDate&blogs-global-accelerator.sort-order=desc&aws-global-accelerator-wn.sort-by=item.additionalFields.postDateTime&aws-global-accelerator-wn.sort-order=desc)
- [Amazon Lex（Alexaと同じテクノロジーを利用した会話型インターフェイス）| AWS](https://aws.amazon.com/jp/lex/)
- [Amazon SageMaker（機械学習モデルを大規模に構築、トレーニング、デプロイ）| AWS](https://aws.amazon.com/jp/sagemaker/)
- [AWS Snowmobile (エクサバイト規模のデータ転送サービス) | AWS](https://aws.amazon.com/jp/snowmobile/)
- [AWS Application Discovery Service（オンプレミスの情報を検出して移行を効率化）| AWS](https://aws.amazon.com/jp/application-discovery/)
- [Amazon QuickSight（あらゆるデバイスからアクセス可能な高速BIサービス）| AWS](https://aws.amazon.com/jp/quicksight/)
- [よくある質問 - Amazon Simple Workflow Service（SWF） | AWS](https://aws.amazon.com/jp/swf/faqs/)
