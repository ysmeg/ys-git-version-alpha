# ブランチを作成

各Stepごとに答えを記載します。

## `mainブランチ`をチェックアウトしていることを確認しましょう

今どこのブランチにいるかは、以下のコマンドをターミナルに入力することで確認できます。

```
% git branch
```

以下の内容が表示されていれば、成功です。

```
* main
```
<br>

## `developブランチ`をチェックアウトしましょう

`mainブランチ`から`developブランチ`に切り替えるには、以下のコマンドを実行します。

```
% git checkout develop
```

以下の内容が表示されていれば、成功です。

```
branch 'develop' set up to track 'origin/develop'.
Switched to a new branch 'develop'
```
<br>

## `developブランチ`から `feature/add-list-item` を作成してください。この時作成したブランチにはチェックアウトしないでください。

新しいブランチを作成するだけの場合、以下のコマンドを実行してください。

```
% git branch feature/add-list-item
```

こちらは実行しても何もログは表示されません。  
そのため以下で再度ブランチが作成されているか確認します。

<br>

## `feature/add-list-item` が作成できたことを確認してください。

ブランチを確認するには、以下のコマンドを実行します。

```
% git branch
```

以下の内容が表示されていれば、成功です。

```
* develop
  feature/add-list-item
  main
```

<br>

## `developブランチ` から `feature/check-type` を作成して同時にチェックアウトしてください。

新しくブランチを作成しつつ、ブランチの切り替えを行うには、以下のコマンドを実行してください。

```
% git checkout -b feature/check-type
```

以下の内容が表示されていれば、成功です。

```
Switched to a new branch 'feature/check-type'
```

<br>

## Practice

[step01の練習問題](../../practice/step01/index.md) へ戻る
