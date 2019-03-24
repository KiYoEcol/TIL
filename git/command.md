### コミットする前の変更を削除する
[色々なgit stash](https://qiita.com/akasakas/items/768c0b563b96f8a9be9d)
```.sh
$git stash save #stashに変更点を記録
$git stash drop　#stashを削除
```

### リモートブランチの残骸を削除する
[ローカルに残ったままのリモートブランチの残骸を削除する](https://statemachine.hatenablog.com/entry/2014/07/16/220007)
```
$git remote prune origin
```

### 履歴でファイル名を表示

```
$git log --name-status
```

### 特定のファイルの変更履歴をみる

```
$ git log {filepath}
```

### 特定のファイルのみバージョンを戻す

```
$ git checkout {hash} {filepath}
```

### キャッシュの削除
.gitignoreが反映されない場合実行すると、反映される~ときがある~

```
$ git rm -r --cached . //ファイル全体キャッシュ削除
$ git rm -r --cached [ファイル名]  //ファイル指定してキャッシュ削除
```
