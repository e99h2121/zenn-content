---
title: "zenn-cli を入れた" # 記事のタイトル
emoji: "😸" # アイキャッチとして使われる絵文字（1文字だけ）
type: "tech" # tech: 技術記事 / idea: アイデア記事
topics: ["初心者", "zenn"] # タグ。["markdown", "rust", "aws"]のように指定する
published: true # 公開設定（falseにすると下書き）
---

https://zenn.dev/zenn/articles/install-zenn-cli 

zenn-cli を入れた。

GitHubリポジトリ: https://github.com/e99h2121/zenn-content

```
npm init --yes # プロジェクトをデフォルト設定で初期化

npm install zenn-cli # zenn-cliを導入

npx zenn init
```

```
npx zenn preview
# 👀 Preview on http://localhost:8000
```

![](/images/for-zenn-content.png)

`zenn-content\images\for-zenn-content.png` と置く。

.gitignore とか全部セットされているからべんり。


## 参考

公式: [Zenn CLIをインストールする](https://zenn.dev/zenn/articles/install-zenn-cli)

[zenn-cliで記事作成してみた](https://zenn.dev/yuta28/articles/first-article-by-cli-yuta)
