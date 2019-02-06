
## エラー例集
### rbindlist
結合したいデータテーブルをlistに格納して渡さないとエラーが発生する

```.R
# エラー発生
rbindlist(d1, d2)
#> rbindlist(d1, d2) でエラー: use.names should be TRUE or FALSE

# 正常終了
rbindlist(list(d1, d2))
```
