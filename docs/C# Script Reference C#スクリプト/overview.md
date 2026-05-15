---
sort: 0
---
# Script Reference overview スクリプトリファレンス概要

C#スクリプトで外部からパッケージに含まれるC#クラスを使用するためのリファレンスです。

## コアコンポーネント
このパッケージは以下のコアコンポーネントで構成されています。

- [ScenarioPlayer](ScenarioPlayer.md): CSVベースのシナリオファイルを読み込み、テキスト表示やキャラクター制御、選択肢の提示などを逐次実行するコアエンジンです。
- [ParamController](ParamController.md): シナリオ内で使用される変数を管理し、セーブ・ロード（JSON形式）をサポートします。スコープ（レベル）に応じた変数の自動クリアも行います。
- [FormulaEvaluator](FormulaEvaluator.md): シナリオ内のテキストや分岐条件に記述された数式や条件式を動的に評価・実行します。`ParamController`と連携して変数の読み書きを行います。
- [ScenarioAnimatorManager](ScenarioAnimatorManager.md): キャラクターやカメラのAnimatorを一元管理し、シナリオ進行とアニメーションの同期、再生完了待ち、スキップ機能などを提供します。


## サポートコンポーネント

コアコンポーネントの使用をサポートするコンポーネント、および`StateMachineBehaviour`クラスです。

- [NovelActivator](NovelActivator.md): インスペクタからCSVシナリオファイルを受け取り、ScenarioPlayerに渡すためのスクリプトです。
- [ScenarioAnimationNotifier](ScenarioAnimationNotifier.md): AnimatorControllerのステートにアタッチし、ステートへの`Enter`または`Exit`を検知してScenarioPlayerに通知するためのスクリプトです。


各クラスの詳細は各スクリプトのページを参照してください。

