---
title: "JavaでQueueを理解するソース" # 記事のタイトル
emoji: "🕘" # アイキャッチとして使われる絵文字（1文字だけ）
type: "tech" # tech: 技術記事 / idea: アイデア記事
topics: ["初心者", "Queue"] # タグ。["markdown", "rust", "aws"]のように指定する
published: true # 公開設定（falseにすると下書き）
---

[スタックとキューを極める！ 〜 考え方と使い所を特集 〜 - Qiita](https://qiita.com/drken/items/6a95b57d2e374a3d3292#2-2-%E3%82%AD%E3%83%A5%E3%83%BC%E3%81%AE%E8%A9%B3%E7%B4%B0)


```java
public class QueueDriver {
    static class Queue {
        final int SIZE = 5;
        private int[] values = new int[SIZE+1];
        private int head = 0;
        private int tail = 0;
        boolean enqueue(int data) {
            if (data < 0) return false;
            if (((tail + 1) % values.length) == head) {
                return false;
            }
            values[tail++] = data;
            tail = tail % values.length;
            return true;
        }
        int dequeue() {
            int data = -1;
            if (tail != head) {
                data = values[head++];
                head = head % values.length;
            }
            return data;
        }
        boolean isEmpty() {
            return (tail == head);
        }
    }
 
    public static void main(String[] args) {
        Queue q = new Queue();
        q.enqueue(1);
        q.enqueue(2);
        q.enqueue(3);
        q.enqueue(4);
        q.enqueue(5);
        q.enqueue(6); // 容量オーバー
        System.out.println(q.dequeue()); // 1
        System.out.println(q.dequeue()); // 2
        q.enqueue(7); // 空きがあるのでデータ保持
        q.enqueue(8); // 空きがあるのでデータ保持
        while (!q.isEmpty()) {
            int data = q.dequeue();
            System.out.print(data+",");
            // 3,4,5,7,8 出力
        }
        System.out.println("");
    }
}
```

```java
import java.util.ArrayDeque;
public class QueueDriver2 {

    public static void main(String[] args) {
        ArrayDeque<Integer> que = new ArrayDeque<Integer>();
        que.add(1);
        que.add(2);
        que.add(3);
        que.add(4);
        que.add(5);
        que.add(6);
        
        for (Integer a : que) {
            System.out.println(a);
        }        
        while (que.size() != 0) {
            System.out.println(que.pop());
        }
    }
}
```