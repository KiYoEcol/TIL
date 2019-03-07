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
