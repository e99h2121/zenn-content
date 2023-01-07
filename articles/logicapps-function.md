---
title: "Logic Apps とか Power Automate で使う関数"
emoji: "⛅"
type: "tech"
topics: ["初心者","Azure"]
published: true
---

[式関数のリファレンス ガイド - Azure Logic Apps | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/logic-apps/workflow-definition-language-functions-reference)


## 特定日まで:

```
less(ticks(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 
     ticks(startOfDay(convertFromUtc('2022-12-31T00:00:00.0000000Z', 'Tokyo Standard Time'))))
```

## 日本時間 9:00 である：

```
and(equals(int(addSeconds(convertFromUtc(utcNow(), 'Tokyo Standard Time'), 5,'HH')), 9), 
    equals(int(addSeconds(convertFromUtc(utcNow(), 'Tokyo Standard Time'), 5,'mm')), 00))
```

## 日本時間 13:00 である：

```
and(equals(int(addSeconds(convertFromUtc(utcNow(), 'Tokyo Standard Time'), 5,'HH')), 13), 
    equals(int(addSeconds(convertFromUtc(utcNow(), 'Tokyo Standard Time'), 5,'mm')), 00))
```


## 平日 (月から金) である：
```
or(equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 1), 
   equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 2),
   equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 3),
   equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 4),
   equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 5))
```

## 週末 (土・日) である：

```
or(equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 6), 
   equals(dayOfWeek(convertFromUtc(utcNow(), 'Tokyo Standard Time')), 0))
```


## 出力とか

```
"or": [
            {
                "equals": [
                    "@outputs('HTTP_2')['statusCode']",
                    404
                ]
            },
            {
                "equals": [
                    "@result('スコープ')[0]['status']",
                    "Succeeded"
                ]
           }
        ]
```


## ほか参考

https://jpazinteg.github.io/blog/LogicApps/ScheduleTriggerStrattime/

