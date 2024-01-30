# リモートリポジトリにプッシュ

各Stepごとに答えを記載します。

## `feature/check-type`をチェックアウトしているか確認しましょう。

どのブランチをチェックアウトしているかは、以下のコマンドを実行します。

```
% git branch
```

`feature/check-type` をチェックアウトしていれば、以下の内容が表示されているはずです。

```
  develop
  feature/add-list-item
* feature/check-type
  main
```

もし上記結果と違う場合は、以下のコマンドを実行して、ブランチを切り替えます。  
(ここでは developブランチ から切り替えることを想定します。)

```
% git checkout feature/check-type
```

以下のように表示されていれば成功です。

```
Switched to branch 'feature/check-type'
```

心配な人は `git branch` コマンドで確認してみてください。

<br>

## 変更したファイルの`状態`を確認しましょう。

変更したファイルの状態を確認するには以下のコマンドを実行してください。

```
% git status
```

以下のように表示されていれば、無事ファイルの変更をgitが検知しています。

```
On branch feature/check-type
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.js

no changes added to commit (use "git add" and/or "git commit -a")
```
<br>

## 変更したファイルを`ステージングエリア`に追加しましょう。

以下のコマンドで変更したファイルをステージングエリアに追加することができます。  

1. 下記は特定のファイルのみをステージングエリアに追加します。

```
% git add [directory/**/file]
```

2. 下記は変更したファイル全てをステージングエリアに追加します。

```
% git add .
```

`git add` コマンドを実行しただけでは、特にログは表示されません。  
再度 `git status` で状態を確認してみましょう。  
以下のように表示されれば、変更したファイルがステージングエリアに追加されています。  

```
On branch feature/check-type
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   index.js
```
<br>

## ステージングエリアにある変更ファイルをローカルリポジトリに`コミット`しましょう。

以下のコマンドでステージングエリアからローカルリポジトリにコミットすることができます。  
今回の条件として、 **コミットする際、「型をチェックする」という`コメント`を追加してください。** とあります。以下のように記載することで、コミットにコメントをつけることが可能です。

```
% git commit -m "型をチェックする"
```

以下の内容が表示されていれば、成功です。  
※ 「280346c」の部分はコミットIDです。そのため人によって内容が変わります。

```
[feature/check-type 280346c] 型をチェックする
 1 file changed, 9 insertions(+), 4 deletions(-)
```
<br>

## ローカルリポジトリにコミットした内容をリモートリポジトリに`プッシュ`しましょう。

ローカルリポジトリからリモートリポジトリにプッシュする場合は、以下のコマンドを実行します。

```
% git push origin feature/check-type
```

または以下でも問題ありません。  
HEADは今作業しているブランチを表しています。

```
% git push origin HEAD
```

以下のような内容が表示されていれば、成功です。

```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 455 bytes | 455.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: 
remote: Create a pull request for 'feature/check-type' on GitHub by visiting:
remote:      https://github.com/(user-name)/(repository-name)/pull/new/feature/check-type
remote: 
To github.com:(user-name)/(repository-name).git
 * [new branch]      HEAD -> feature/check-type
```

<br>

## practice

[step02の練習問題](../../practice/step02/index.md) へ戻る
