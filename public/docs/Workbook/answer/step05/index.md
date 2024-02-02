## step04 までの復習

以下、解答になります。

### step. 01

#### ブランチ確認

答え

```
% git branch
```

実行結果

```
  develop
* feature/create-components
  main
```

#### ブランチの切り替え

※ feature/create-components をチェックアウトができていれば、ここはスキップしてください。

答え

```
% git checkout feature/create-components
```

実行結果

```
Switched to branch 'feature/create-components'
```

### step. 02

問題内容の通りにファイルを更新してください。

### step. 03

答え

```
% git status
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
On branch feature/create-components
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   src/App.tsx

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        src/components/InputForm/
        src/components/List/

no changes added to commit (use "git add" and/or "git commit -a")
```

### step. 04

答え

```
% git add .
```

実行結果は特に表示されません。

### step. 05

答え

```
% git status
```

実行結果

```
On branch feature/create-components
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   src/App.tsx
        new file:   src/components/InputForm/index.tsx
        new file:   src/components/List/index.tsx
```

### step. 06

答え

```
% git commit -m "ここに任意のコミットメッセージを入力します"
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
[feature/create-components <コミットIDが表示されます>] <入力されたコミットメッセージが表示されます>
 3 files changed, 199 insertions(+), 155 deletions(-)
 create mode 100644 src/components/InputForm/index.tsx
 create mode 100644 src/components/List/index.tsx
```

### step. 07

答え

```
% git status
```

実行結果

```
On branch feature/create-components
nothing to commit, working tree clean
```

### step. 08

答え

```
% git push origin feature/create-components

or

% git push origin HEAD
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
Enumerating objects: 13, done.
Counting objects: 100% (13/13), done.
Delta compression using up to 8 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (9/9), 2.74 KiB | 2.74 MiB/s, done.
Total 9 (delta 2), reused 2 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: This repository moved. Please use the new location:
remote:   git@github.com:ys-nkjm/ys-git-version-alpha.git
remote: 
remote: Create a pull request for 'feature/create-components' on GitHub by visiting:
remote:      https://github.com/ys-nkjm/ys-git-version-alpha/pull/new/feature/create-components
remote: 
To github.com:ys-nkjm/ys-git-version-alpha.git
 * [new branch]      feature/create-components -> feature/create-components
```

### step. 09
#### マージ先を develop ブランチにしてください。

画像の赤枠のボタンをクリックして、develop ブランチを指定してください。

![ブランチ変更](/public/images/workbook/step05/answer/image-01.png)

#### Open 状態でプルリクエストを作成してください。

画像赤枠の ▼ ボタンをクリックして、Create pull request をクリックしてください。

![Open で作成](/public/images/workbook/step05/answer/image-02.png)

### step. 10
プルリクエストをマージするには、画像赤枠の Merge pull request ボタンをクリックしてください。

![Merge pull request](/public/images/workbook/step05/answer/image-03.png)

次に Confirm merge ボタンをクリックしてください。

![Confirm merge](/public/images/workbook/step05/answer/image-04.png)

### step. 11

マージ後、不要ブランチを削除するには、Delete branch ボタンをクリックしてください。

![Delete branch](/public/images/workbook/step05/answer/image-05.png)

### step. 12

#### develop ブランチに切り替えてください。

答え

```
% git checkout develop
```

実行結果

```
Switched to branch 'develop'
Your branch is up to date with 'origin/develop'.
```

#### ローカルリポジトリの履歴を最新にする

答え

```
% git fetch --prune
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
From github.com:ys-nkjm/ys-git-version-alpha
 - [deleted]         (none)     -> origin/feature/create-components
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 952 bytes | 476.00 KiB/s, done.
   cd2a982..1b7609c  develop    -> origin/develop
```

#### ローカルで不要になったブランチを削除する

答え

```
% git branch -D feature/create-components
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
Deleted branch feature/create-components (was 3da2e43).
```

### step. 13

答え

```
% git pull origin develop
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
From github.com:ys-nkjm/ys-git-version-alpha
 * branch            develop    -> FETCH_HEAD
Updating cd2a982..1b7609c
Fast-forward
 src/App.tsx                        | 163 ++++-------------------------------------------------------------------
 src/components/InputForm/index.tsx |  76 +++++++++++++++++++++++++++++++++
 src/components/List/index.tsx      | 115 ++++++++++++++++++++++++++++++++++++++++++++++++++
 3 files changed, 199 insertions(+), 155 deletions(-)
 create mode 100644 src/components/InputForm/index.tsx
 create mode 100644 src/components/List/index.tsx
```

## practice

[練習問題](/public/docs/Workbook/practice/step05/index.md) へ戻る
