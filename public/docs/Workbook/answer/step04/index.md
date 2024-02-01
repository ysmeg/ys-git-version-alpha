## 最新の変更を取り込む

各Stepごとに答えを記載します。

### step. 01

答え

```
% git checkout develop
```

実行結果

```
Switched to branch 'develop'
Your branch is up to date with 'origin/develop'.
```

### step. 02

答え

```
% git branch -D feature/create-todo-app
```

実行結果

```
Deleted branch feature/create-todo-app (was c4e0027).
```

### step. 03

答え

```
% git fetch --prune
```

実行結果

```
From github.com:ys-nkjm/ys-git-training-fizz-buzz
 - [deleted]         (none)     -> origin/feature/create-todo-app
```

### step. 04

答え

```
% git pull origin develop
```

実行結果  
※ 表示される内容が多少異なることがございます。

```
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 919 bytes | 459.00 KiB/s, done.
From github.com:ys-nkjm/ys-git-training-fizz-buzz
 * branch            develop    -> FETCH_HEAD
   ba628e2..cd2a982  develop    -> origin/develop
Updating ba628e2..cd2a982
Fast-forward
 src/App.tsx | 177 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++---
 1 file changed, 173 insertions(+), 4 deletions(-)
```

### step. 05

答え

```
% git checkout feature/create-components
```

実行結果

```
Switched to branch 'feature/create-components'
```

### step. 06

答え

```
% git rebase develop
```

実行結果

```
Successfully rebased and updated refs/heads/feature/create-components.
```

## practice

[練習問題](/public/docs/Workbook/practice/step04/index.md) へ戻る
