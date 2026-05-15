---
sort: 2
---

# NovelActivator

インスペクタからCSVシナリオファイルを受け取り、ScenarioPlayerに渡すためのスクリプトです。

## 主な機能

- インスペクタウィンドウでCSVファイルのリストを受け取ります
- Buttonコンポーネントの`OnClick`等に`NovelActivator.ActivateNovelPlayer`を登録することで、ボタンを押すとシナリオの再生を開始します
- インスペクタウィンドウで`callback`に`UnityEvent`を登録すると、シナリオ再生完了時にそのイベントが実行されます。

## 使用例

### マップ上のオブジェクトに設定する

以下の手順で、マップ上に配置されたSpriteをクリックしたときにシナリオを再生する機能を実装します。

1. クリックするオブジェクトのインスペクタウィンドウに`NovelActivator`コンポーネントを追加します
> [!Note]-開発者メモ
> 実はどのオブジェクトに付けても問題ありません。トリガーとなる`Button`の`OnClick`で`NovelActivator.ActivateNovelPlayer`を呼び出すことでシナリオが再生されます。
> しかし、シナリオがどのボタンに紐づいているかわかりにくくなるので、表示させたいSpriteと同じオブジェクトに設定するのがおすすめです。

2. `ScenarioFiles`にCSVファイルをアタッチします
3. `Callback`の各要素にコールバックイベントを登録します
    - オブジェクトのSpriteを再表示するために、`SpriteRenderer.enabled = true`を登録します。
4. オブジェクトに`Button`コンポーネントを追加し、`OnClick`に
    - `NovelActivator.ActivateNovelPlayer`
    - `SpriteRenderer.enabled = false`
    を登録します。

5. Playモードに入り、Spriteをクリックしてシナリオが再生されるのを確認します。

## public プロパティ
### scenarioFiles
インスペクタで設定されたシナリオファイルです。

### callback
シナリオ再生完了時に実行されるコールバックです。

## public static メソッド
### ActivateNovelPlayer
インスペクタで登録された`scenarioFiles`を順番に再生します。

#### シグネチャ
```csharp
public static void ActivateNovelPlayer(TextAsset scenarioFile)
```

#### パラメータ
| 名前 | 型 | 説明 |
|---|---|---|
| `scenarioFile` | `TextAsset` | 再生するシナリオファイル |
