---
title: "Kusto クエリ完全理解"
emoji: "⛅"
type: "tech"
topics: ["初心者","Azure"]
published: true
---


## Kusto クエリ
- KQL 
	- Kusto（KQL: Kusto Query Language）とは、Azure のモニタリング製品（Application Insight、Log Analytics など）や Data Explorer で使用されるデータの問い合わせ言語
- [Kusto クエリのサンプル - Azure Data Explorer | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/data-explorer/kusto/query/samples?pivots=azuremonitor)
- 以下でお試しできる
	- [help.Samples | Azure Data Explorer](https://dataexplorer.azure.com/clusters/help/databases/Samples)
- 一般的な SELECT 文をほうふつさせるもの
	- [チュートリアル: Kusto クエリ | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/data-explorer/kusto/query/tutorial?pivots=azuredataexplorer)

```
StormEvents | count
```
- 文字列操作 みたいなこともできる

```
print "this is a 'string' literal in double \" quotes"
```

- で、それが [Azure Monitor Logs - Connectors | Microsoft Learn](https://learn.microsoft.com/ja-jp/connectors/azuremonitorlogs/#%E3%82%AF%E3%82%A8%E3%83%AA%E3%82%92%E5%AE%9F%E8%A1%8C%E3%81%97%E3%81%A6%E7%B5%90%E6%9E%9C%E3%82%92%E4%B8%80%E8%A6%A7%E8%A1%A8%E7%A4%BA%E3%81%99%E3%82%8B) など、Logic Apps でもつかえる
- SQL 言語のサブセットもサポートされている
	- [SQL から Kusto へのクエリの変換 - Azure Data Explorer | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/data-explorer/kusto/query/sqlcheatsheet)

## 参考
- [Kusto 照会言語 (KQL) の概要 - Azure Data Explorer | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/data-explorer/kusto/query/)
- [Kusto 王への道 (1) - 基本 - Qiita](https://qiita.com/TsuyoshiUshio@github/items/08a1ee8ca3e1c87ee2dc)
