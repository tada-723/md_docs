```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  @oerride
  Widget build(BuildContext context) {
    const MyApp({Key? key}) : super(key: key);
    final title = 'Flutterサンプルサンプル';
    final message = 'サンプル・メッセージ';

    @override
    Widget build(BuildContext context) {
      return MaterialApp(
        title: 'Flutter Demo',
        theme: MyHomePage(
          title: this.title,
          message: this.message,

        ),
      );
    }
  }
}
class MyHomePage extends StatelessWidget {
  const MyHomePage({Key? key, required this.title, required this.message})
      : super(key: key);
  final String title;
  final String message;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: Text(
        widget.message,
        style: TextStyle(fontSize: 32.0),
      ),
    );
  }
}
```

- `main()` 関数 → `runApp()` でアプリ起動。
- `MyApp` ウィジェットがアプリのエントリーポイント。
- `MaterialApp` を使ってアプリのテーマやルート設定をする。
- `main()` 関数 → `runApp()` でアプリ起動。
- `MyApp` ウィジェットがアプリのエントリーポイント。
- `MaterialApp` を使ってアプリのテーマやルート設定をする。
- `MyApp` → `MyHomePage` に `title` と `message` を渡す。
- Flutter では **親から子** へのデータ伝搬が明確かつ簡潔。
- `Scaffold` を使用して、`AppBar` と `body` を構築。
- `AppBar` にタイトルを設定し、`body` には中央寄せの `Text` を表示。
- `Text` ウィジェットに `TextStyle(fontSize: 32.0)` を指定して大きめのフォントを使用。
- `const` を使うことで、ウィジェットの再ビルドを抑えられ、パフォーマンスが向上。
- Flutterでは可能な限り定数コンストラクタ（`const`）を使用するのがベストプラクティス。
