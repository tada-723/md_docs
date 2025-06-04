
---

##  AppBarとは？

`AppBar` は、`Scaffold` ウィジェットの `appBar` プロパティで使用されます。
主に **画面の上部（トップバー）に配置され、ユーザーに情報や操作手段を提供する**役割を果たします。

---

##  基本的な使い方

```dart
Scaffold(
  appBar: AppBar(
    title: Text('アプリのタイトル'),
  ),
  body: Center(child: Text('本文')),
);
```

---

## 🔧 AppBarでできること

| 機能                  | 説明                                   | コード例                 |
| ------------------- | ------------------------------------ | -------------------- |
| **タイトル**            | 中央に表示されるテキスト                         | `title: Text('ホーム')` |
| **背景色の変更**          | `backgroundColor: Colors.blue` などで設定 |                      |
| **左側の戻るボタン/メニュー**   | `leading: Icon(Icons.menu)`          |                      |
| **右上のアイコンボタン**      | `actions: [IconButton(...)]`         |                      |
| **影（elevation）**    | `elevation: 4.0`（影の深さ）               |                      |
| **中央寄せ（iOS風）**      | `centerTitle: true`                  |                      |
| **フラットAppBar（影なし）** | `elevation: 0`                       |                      |

---

###  アクション付きAppBar

```dart
AppBar(
  title: Text('My App'),
  actions: [
    IconButton(
      icon: Icon(Icons.search),
      onPressed: () {
        print('検索アイコン押下');
      },
    ),
    IconButton(
      icon: Icon(Icons.settings),
      onPressed: () {
        print('設定アイコン押下');
      },
    ),
  ],
),
```

###  カスタム背景色とテキストスタイル

```dart
AppBar(
  backgroundColor: Colors.teal,
  title: Text(
    'カスタムAppBar',
    style: TextStyle(color: Colors.white),
  ),
  iconTheme: IconThemeData(color: Colors.white),
),
```

---

##  注意点

* `AppBar` は基本的に `Scaffold` の中で使う。
* `actions` に複数のアイコンを設定できるが、**3個以上になると詰まりやすい**ため注意。
* `leading` を設定しないと、`Navigator` が戻るボタンを自動で追加します（iOSスタイル）。

---

##  UI的なイメージ

```
+----------------------------------------------------+
| ← タイトル                                     ⚙️ 🔍 |
+----------------------------------------------------+
```

---

##  まとめ

| 項目                | 説明                  |
| ----------------- | ------------------- |
| `title`           | アプリのタイトルや画面名を表示     |
| `actions`         | 右上のアイコンボタン（例：検索、設定） |
| `leading`         | 左側のアイコン（例：戻る、メニュー）  |
| `backgroundColor` | 背景色                 |
| `elevation`       | 影の深さ                |
| `centerTitle`     | タイトル中央寄せ            |

---
