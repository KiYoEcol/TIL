## カタカナ判定

```.R
grep("[ア-ン]", "テスト", value = TRUE)
#> [1] "テスト"

grep("[ア-ン]", "てすと", value = TRUE)
#> character(0)

grep("[ア-ン]", "test", value = TRUE)
#> character(0)
```
