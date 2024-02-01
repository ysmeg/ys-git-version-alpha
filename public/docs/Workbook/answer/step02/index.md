## コミット・プッシュ

各Stepごとに答えを記載します。

### step. 01

答え

```
% git branch
```

実行結果

```
  develop
  feature/create-components
* feature/create-todo-app
  main
```

feature/create-todo-app をチェックアウトしていない場合は以下のコマンドを実行してください。

```
% git checkout feature/create-todo-app
```

実行結果

```
Switched to branch 'feature/create-todo-app'
```

### step. 02

問題内容の通りにファイルを更新してください。

### step. 03

答え

```
% git status
```

実行結果

```
On branch feature/create-todo-app
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   src/App.tsx

no changes added to commit (use "git add" and/or "git commit -a")
```

### step. 04

#### パターン01

答え

```
% git add src/App.tsx
```

実行結果は特に表示されません。

#### パターン02

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
On branch feature/create-todo-app
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   src/App.tsx
```

### step. 06

答え

```
% git commit -m "ここに任意のコミットメッセージを入力します"
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
[feature/create-todo-app <コミットIDが表示されます>] <入力されたコミットメッセージが表示されます>
 1 file changed, 173 insertions(+), 4 deletions(-)
```

### step. 07

答え

```
% git status
```

実行結果

```
On branch feature/create-todo-app
nothing to commit, working tree clean
```

### step. 08

答え

```
git push origin feature/create-todo-app
```

または

```
git push origin HEAD
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 1.62 KiB | 1.62 MiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: This repository moved. Please use the new location:
remote:   git@github.com:ys-nkjm/ys-git-training-test.git
remote: 
remote: Create a pull request for 'feature/create-todo-app' on GitHub by visiting:
remote:      https://github.com/ys-nkjm/ys-git-training-test/pull/new/feature/create-todo-app
remote: 
To github.com:ys-nkjm/ys-git-training-fizz-buzz.git
 * [new branch]      HEAD -> feature/create-todo-app
```


## practice

[練習問題](/public/docs/Workbook/practice/step02/index.md) へ戻る
