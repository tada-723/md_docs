---

# Flutterの `Column` と `Row` の基本

---

## Column の使用方法

`Column` を使用すると、**縦方向**にテキストやウィジェットを並べることができます。

### 基本形

```dart
new Column(
  mainAxisAlignment: MainAxisAlignment.start,
  mainAxisSize: MainAxisSize.max,
  crossAxisAlignment: CrossAxisAlignment.center,
  children: <Widget>[
    // 子ウィジェットをここに追加
  ]
)
```

* `children` に指定したリストの順番で、**上から下へ**ウィジェットが表示されます。

---

## 📏 Row の使用方法

`Row` を使用すると、**横方向**にテキストやウィジェットを並べることができます。

### ✅ 基本形

構造は `Column` とほぼ同じで、**縦**ではなく**横**に並ぶ点が異なります。

```dart
new Row(
  mainAxisAlignment: MainAxisAlignment.start,
  mainAxisSize: MainAxisSize.max,
  crossAxisAlignment: CrossAxisAlignment.center,
  children: <Widget>[
    // 子ウィジェットをここに追加
  ]
)
```

* 必要に応じて、`mainAxisAlignment` や `crossAxisAlignment` を調整することで、より細かいレイアウト制御が可能です。

---
