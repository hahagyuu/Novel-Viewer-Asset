---
sort: 4
---

# FormulaEvaluator

文字列で渡された数式や条件式を評価し、結果を返すための計算エンジンです。

## 主な機能

- **動的評価 (`Evaluate`)**: `Money >= 100` や `{Score} + 10` のような式をパースし、真偽値や数値を計算します。
- **動的実行 (`Execute`)**: `Money += 100` や `Flag = 1` などの代入式を実行します。
- **変数連携**: デフォルトでは `ParamController.Instance` と連携し、変数の値を取得・更新します。カスタムの Getter/Setter デリゲートに置き換えることで、独自の変数管理システムとも連携可能です。

## 使い方

- 評価: `bool result = FormulaEvaluator.Evaluate("A == B").ToBoolean();`
- 実行: `FormulaEvaluator.Execute("A += 100");`
