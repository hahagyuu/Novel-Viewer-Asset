# FukayaGames Scenario System

Unity向けの汎用シナリオ・パラメータ制御システムです。このパッケージは以下のコアコンポーネントで構成されています。

## コアコンポーネント

- [ScenarioPlayer](ScenarioPlayer.md): CSVベースのシナリオファイルを読み込み、テキスト表示やキャラクター制御、選択肢の提示などを逐次実行するコアエンジンです。
- [ParamController](ParamController.md): シナリオ内で使用される変数を管理し、セーブ・ロード（JSON形式）をサポートします。スコープ（レベル）に応じた変数の自動クリアも行います。
- [FormulaEvaluator](FormulaEvaluator.md): シナリオ内のテキストや分岐条件に記述された数式や条件式を動的に評価・実行します。`ParamController`と連携して変数の読み書きを行います。
- [ScenarioAnimatorManager](ScenarioAnimatorManager.md): キャラクターやカメラのAnimatorを一元管理し、シナリオ進行とアニメーションの同期、再生完了待ち、スキップ機能などを提供します。

## クイックスタート

1. `ScenarioPlayer` コンポーネントをシーン内の GameObject にアタッチします。
2. インスペクタで必要な UI 設定（WindowEntryやSelectBox）と設定用 CSV（CharacterSettingsCsv, CameraSettingsCsv）を割り当てます。
3. `ParamController`, `ScenarioAnimatorManager` をそれぞれシーン内に配置します。
4. スクリプトから `ScenarioPlayer.Instance.Activate()` を呼び出してシナリオを開始します。
