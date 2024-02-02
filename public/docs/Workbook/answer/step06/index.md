## コンフリクトの解消

以下、解答になります。

### step. 01
画像上部の赤枠で囲まれている Pull requests タブからプルリクスト一覧画面を表示します。

画像赤枠で囲まれている New pull request から新規プルリクエストを作成することができます。

![New pull request](/public/images/workbook/step06/answer/image-01.png)

まずプルリクエストを出したいブランチを選択します。  
compare: main と書かれているセレクトボタンから feature/use-json-server を選択してください。

![change compare branch](/public/images/workbook/step06/answer/image-02.png)

次にマージ先となるブランチを選択します。  
base: main と書かれているセレクトボタンから develop を選択してください。

![change base branch](/public/images/workbook/step06/answer/image-03.png)

対象ブランチ feature/use-json-server 、マージ先ブランチ develop とできたら、Create pull request ボタンを押下して、プルリクエスト作成画面を表示させます。

![Create pull request 01](/public/images/workbook/step06/answer/image-04.png)

タイトル、説明文を記載が完了したら、Create pull request ボタンを押下してください。  
新規プルリクエストが作成されます。

![Create pull request 02](/public/images/workbook/step06/answer/image-05.png)

### step. 02

#### コンフリクトが起きていることを確認する

プルリクエストページ下部に、画像赤枠の表示があればコンフリクトが発生していることが確認できます。

![check conflict](/public/images/workbook/step06/answer/image-06.png)

#### コマンドでコンフリクトを解消する

##### develop をチェックアウトする

答え

```
% git checkout develop
```

実行結果

```
Switched to branch 'develop'
Your branch is up to date with 'origin/develop'.
```

#### develop ブランチを最新にする
<small>
  前 step で行っているため、差分はないかと思います。<br>
  ただコンフリクトが起きた場合は、念の為毎回ブランチを最新化してから行った方が良いため、今回も実行します。
</small>

<br>

答え

```
% git pull origin develop
```

実行結果

```
From github.com:ys-nkjm/ys-git-version-alpha
 * branch            develop    -> FETCH_HEAD
Already up to date.
```

##### feature/use-json-server をチェックアウトする

答え

```
% git checkout feature/use-json-server
```

実行結果

```
Switched to branch 'feature/use-json-server'
```

##### ローカルの develop ブランチを feature/use-json-server にマージする

答え

```
% git merge develop
```

実行結果

```
Auto-merging src/App.tsx
CONFLICT (content): Merge conflict in src/App.tsx
Auto-merging src/components/InputForm/index.tsx
CONFLICT (add/add): Merge conflict in src/components/InputForm/index.tsx
Auto-merging src/components/List/index.tsx
CONFLICT (add/add): Merge conflict in src/components/List/index.tsx
Automatic merge failed; fix conflicts and then commit the result.
```

##### コンフリクトが起きているファイルを開き、コンフリクトを解消する

上記ログにコンフリクトが起きているファイルが書かれています。

- src/App.tsx
- src/components/InputForm/index.tsx
- src/components/List/index.tsx

これらのファイルを開いてください。  
<small>今回は src/App.tsx を例に進めます。他ファイルも例を参考に直してみてください。</small>

src/App.tsx を開くと画像のようになっている箇所があります。

HEAD と書かれている緑色の部分は feature/use-json-server ブランチで修正したコードです。

![conflict HEAD](/public/images/workbook/step06/answer/image-07.png)

develop と書かれている青色部分は、merge コマンドで取り込んだ develop ブランチのコードになります。

![conflict develop](/public/images/workbook/step06/answer/image-08.png)

この差分の見方が把握しづらい場合は、「変更を比較」を選択することで見やすくなります。

![check different](/public/images/workbook/step06/answer/image-09.png)

![check different](/public/images/workbook/step06/answer/image-10.png)

今回は feature/use-json-server を取り込みたいので、HEAD の内容を取り込みます。  
画像では HEAD の横に「(現在の変更)」と表示されています。その文言に従い、「現在の変更を取り込む」を選択してください。

![select current change](/public/images/workbook/step06/answer/image-11.png)

「現在の変更を取り込む」を選択すると、画像のように自動で「(現在の変更)」箇所が残されます。

![resolve conflict](/public/images/workbook/step06/answer/image-12.png)

他の差分も同じようにコードを確認して解消してください。  
**※ src/App.tsx で import している path にエラーが残っているので、再度 import しなおしてください。エラーが消えると思います。**

### step. 03
<div style=" border: 1px solid red; padding: 5px;">
  <strong style="color: red; text-shadow: 1px 1px 1px black">
    ⚠️ 警告
  </strong><br>
  <strong style="color: red; text-shadow: 1px 1px 1px black">
    ‼️step. 03 以降は、全てのコンフリクトを解消してから進めてください‼️
  </strong>
</div>

<br>

答え

```
% git add .
```

実行結果は表示されません。

### step. 04

答え

```
% git commit
```

実行結果

```
Merge branch 'develop' into feature/use-json-server

# Conflicts:
#       src/App.tsx
#       src/components/InputForm/index.tsx
#       src/components/List/index.tsx
#
# It looks like you may be committing a merge.
# If this is not correct, please run
#       git update-ref -d MERGE_HEAD
# and try again.


# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch feature/use-json-server
# All conflicts fixed but you are still merging.
#
# Changes to be committed:
#       modified:   src/components/InputForm/index.tsx
#
```

#### vim コマンド

コミットした時に、ターミナルに上記のメッセージが作成されます。  
このメッセージを完了するには、以下の vim コマンドを利用します。

<div style=" border: 1px solid yellow; padding: 5px;">
  <strong style="color: yellow; text-shadow: 1px 1px 1px black">
    ⚠️ 注意
  </strong><br>
  <strong style="color: yellow; text-shadow: 1px 1px 2px black">
    下部に「-- INSERT --」と出ていないことを確認してください。<br>
    出ている場合は、 escape ボタンを押下し、消えていることを確認してから進めてください。
  </strong>
</div>

<br>

```
!wq
```

これは「**保存して終了**」という意味になります。  
上記コマンドを実行して、以下のメッセージが返ってきたら成功しています。

```
[feature/use-json-server eb81da6] Merge branch 'develop' into feature/use-json-server
```

念の為、ステージングエリアに変更ファイルが残っていないか確認しましょう。

```
% git status
```

実行結果

```
On branch feature/use-json-server
nothing to commit, working tree clean
```

### step. 05

答え

```
% git push origin feature/use-json-server
```

実行結果

```
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 572 bytes | 572.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote: This repository moved. Please use the new location:
remote:   git@github.com:ys-nkjm/ys-git-version-alpha.git
To github.com:ys-nkjm/ys-git-version-alpha.git
   7919250..eb81da6  feature/use-json-server -> feature/use-json-server
```

Github でプルリクエストを確認した時に、画像赤枠のようになっていれば、コンフリクトは無事解消されています。

![resolve conflict](/public/images/workbook/step06/answer/image-13.png)

### step. 06 ~ 09

こちらは今まで行ってきた操作と同じになるため、割愛します。  
もう一度確認したい場合は [step. 05](/public/docs/Workbook/answer/step05/index.md#step-09) をご確認ください。

## practice

[練習問題](/public/docs/Workbook/practice/step06/index.md) へ戻る
