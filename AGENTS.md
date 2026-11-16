# Local Codex Agent Rules — YukariNotes

対象: Android用プリコネ非公式情報アプリ。Kotlin/JavaとGradleでビルド。

## Loop Engineering（2026-11-17）
- [固有の開発・試験ループ](docs/LOOP_ENGINEERING.md)、[Codex再開指示](prompts/CODEX_LOOP.md)を先に読む。
- README等の既存仕様・停止指示を尊重。1起動1件の小タスクを現状→仮説→実装→テスト→評価→次タスクとする。
- READYなしでも未完了を確認するが、存在しない課題は作らない。外部操作や本番変更の承認を迂回しない。
