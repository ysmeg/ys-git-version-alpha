# upstream

upstreamとは、特定のローカルブランチが、特定のリモートブランチの履歴を追跡するように設定することです。  

<br>

## 設定方法

```
% git branch --set-upstream-to=origin/<target remote branch name> <local branch name>
```

## upstreamが設定されているか確認

```
% git branch -vv
```

以下のような情報が返ってきます。

```
  feature/check-type commitId CommitMessage
* develop            commitId [origin/develop] CommitMessage
  main               commitId [origin/main] CommitMessage
```

履歴追跡の設定していあるブランチには `[origin/develop]` のような記述があります。

<br>

## 設定することで何が良いか？

1. 設定していないと、毎回以下のようなコマンドを打つ必要がある

```
% git pull origin main
```

2. ブランチ名の打ち間違いが防げる  
mainブランチやdevelopブランチはpullする対象が、決まっているので設定しておくことでブランチ名の入力間違い（人的ミス）が防げる。
