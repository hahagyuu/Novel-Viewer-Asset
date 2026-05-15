---
sort: 5
---

# ScenarioAnimatorManager

シーン内のキャラクターやカメラの Animator を一元管理し、シナリオ進行とアニメーションの同期を取るシステムです。

## 主な機能

- **パラメータ設定**: `ScenarioPlayer` から送られるコマンド引数（Trigger, Bool, Float, Int等）をパースし、対象の Animator に適用します。
- **再生待ちとスキップ**: `isSkippable` フラグに応じて、アニメーションの再生完了を待機したり、プレイヤーのクリック入力で強制的にスキップ（遷移）させることができます。

## 使い方

インスペクタ上で `globalAnimators` にシーン内の各 Animator を登録しておきます。
シナリオ進行に伴い、`ScenarioPlayer` が内部的に `SetAnimatorParam` を呼び出してアニメーションを制御するため、通常は他スクリプトから直接呼び出す必要はありません。
