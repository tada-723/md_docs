---

## 🧩 `showDialog`関数とは？

Flutter における `showDialog` 関数は、**ダイアログ（モーダルなポップアップ）を画面上に表示するための関数**です。
ユーザーに通知したり、確認を求めたり、選択をさせたりするために使われます。

---

## 基本的な構文

```dart
showDialog(
  context: context,
  builder: (BuildContext context) {
    return AlertDialog(
      title: Text('タイトル'),
      content: Text('内容'),
      actions: [
        TextButton(
          onPressed: () {
            Navigator.of(context).pop(); // ダイアログを閉じる
          },
          child: Text('OK'),
        ),
      ],
    );
  },
);
```

---

## ✨ 何ができるの？

| 用途         | 具体例                                         |
| ---------- | ------------------------------------------- |
| ✅ ユーザーへの通知 | 「保存が完了しました」などのメッセージ表示                       |
| ✅ 確認ダイアログ  | 「本当に削除しますか？」のような確認                          |
| ✅ 入力フォーム表示 | ダイアログ内で `TextField` を使ってユーザーに入力させる          |
| ✅ カスタムUI   | `AlertDialog` の中に任意のウィジェットを組み込んで自由なレイアウトが可能 |

---

## 🛠 カスタム例：OK/キャンセル確認

```dart
showDialog(
  context: context,
  builder: (context) => AlertDialog(
    title: Text('確認'),
    content: Text('本当に削除しますか？'),
    actions: [
      TextButton(
        onPressed: () => Navigator.of(context).pop(false), // キャンセル
        child: Text('キャンセル'),
      ),
      ElevatedButton(
        onPressed: () => Navigator.of(context).pop(true), // OK
        child: Text('削除'),
      ),
    ],
  ),
).then((result) {
  if (result == true) {
    // ユーザーが「削除」を押したときの処理
  }
});
```

---

## 🧠 補足

* ダイアログを閉じるには `Navigator.of(context).pop()` を使います。
* `showDialog` は `Future` を返すため、`then()` や `await` を使ってユーザーの選択を受け取れます。
* ダイアログは **画面上に重ねて表示され、他の操作をブロック**します。

---
