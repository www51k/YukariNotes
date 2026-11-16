# Loop Engineering — YukariNotes

対象: Android用プリコネ非公式情報アプリ。Kotlin/JavaとGradleでビルド。
正本候補: README.md、app/src、既存Gradle設定、UI/端末別試験

## 1サイクルの実行
1. 現状: AGENTS.md/README/Issue/未コミット変更/失敗記録を確認。
2. 選定: READYがなくても実在する未完了を切り出し、独立した安全な最小タスクを1件選ぶ（候補: 既存issueやテストに再現根拠があるAndroidの小不具合/既存unit test不足1件）。根拠がなければNO_TASK。
3. 仮説: 再現条件・修正範囲・合格条件を定義。
4. 実装: 許可済みのワークツリー内のみ最小変更。
5. 検証: ./gradlew :app:assembleDebug および利用可能な既存unit test。テスト不能をPASSとしない。
6. 評価: PASS/BLOCKED_INPUT/BLOCKED_ENV/TEST_INFRA_ERROR/TASK_FAILを実測で分類。
7. 引継ぎ: 変更ファイル、検証ログ、未確認条件、次タスク1件を記録。

## 安全と実行条件
署名用local.properties・release keystore・個人情報を表示/変更しない。自動公開しない。。同一失敗への無根拠再試行禁止。ブロックしても別の独立案件に進む。停止指示を維持し、結果不明の副作用は照合。ループ処理を無限に継続するのではなくOSスケジューラーが次回を起動する。監視だけでは開発成果でない。

報告: task_id｜仮説｜変更ファイル｜検証と結果｜分類｜ブロッカー｜次のタスク。
