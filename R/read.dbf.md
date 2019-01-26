### dbfファイルを読み込む
シェープファイルに付属のdbfファイルを読み込む

``` .R
# ファイルの読み込み。as.is = T で文字列がFactorになるのを防ぐ。
data <- foreign::read.dbf("filePath.dbf", as.is = T)
```
