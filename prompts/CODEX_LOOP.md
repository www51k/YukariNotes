# YukariNotes / Codex Loop Engineering Prompt

AGENTS.md と docs/LOOP_ENGINEERING.md、README.md、app/src、既存Gradle設定、UI/端末別試験 を確認し、確実に未完了な小タスク1件を選定。READYがなくても既存記録から独立タスクを探すが、未完了の証拠がない場合はNO_TASK。候補: 既存issueやテストに再現根拠があるAndroidの小不具合/既存unit test不足1件。

1回の実行で現状→仮説→最小変更→./gradlew :app:assembleDebug および利用可能な既存unit test→PASS/BLOCKED_INPUT/BLOCKED_ENV/TEST_INFRA_ERROR/TASK_FAIL分類→次タスク引継ぎを実施する。署名用local.properties・release keystore・個人情報を表示/変更しない。自動公開しない。。

実コード差分と検証結果が確認できない場合はPASSとしない。出力はtask_id、変更ファイル、テスト/結果、状態、残課題、次の独立タスク。push/公開/実機/本番/秘密情報への変更は禁止。定期実行は別途OS側設定を要する。


## progress.md対応
- 既存タスクとコードの状態を確認したうえでルート `progress.md` を読み、実行後にコード差分・テスト結果・次の独立タスクを記録する。
- 進捗更新だけで完了扱いにせず、指示対象でも権限未確認なら実行・送信しない。
