
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

### pforeach + data.table
pforeach内部でdata.tableを使う際にfunctionにしないとエラーが発生する

```.R
d1 <- data.table(id = 1:10, dummy1 = runif(10))
d2 <- data.table(id = 1:10, dummy1 = runif(10))

# これだとエラー
result <- pforeach(i = 1:nrow(d1), .combine = rbind)({
  library(data.table)
  
  tmp <- rbindlist(list(d1[i,],d2[i,]))
  tmp[,list(dummy1 = sum(dummy1)), by = 'id']
})
print(result)
#>          message                                call      
#>result.1  " オブジェクト 'dummy1' がありません " Expression
#>result.2  " オブジェクト 'dummy1' がありません " Expression
#>result.3  " オブジェクト 'dummy1' がありません " Expression
#>result.4  " オブジェクト 'dummy1' がありません " Expression
#>result.5  " オブジェクト 'dummy1' がありません " Expression
#>result.6  " オブジェクト 'dummy1' がありません " Expression
#>result.7  " オブジェクト 'dummy1' がありません " Expression
#>result.8  " オブジェクト 'dummy1' がありません " Expression
#>result.9  " オブジェクト 'dummy1' がありません " Expression
#>result.10 " オブジェクト 'dummy1' がありません " Expression

# これだとOK
fun1 <- function(i){
  library(data.table)
  
  tmp <- rbindlist(list(d1[i,],d2[i,]))
  tmp[,list(dummy1 = sum(dummy1)), by = 'id']
}
result <- pforeach(i = 1:nrow(d1), .combine = rbind)({
  fun1(i)
})
print(result)
#>    id    dummy1
#> 1:  1 1.5298708
#> 2:  2 1.0479946
#> 3:  3 0.5619589
#> 4:  4 1.1892549
#> 5:  5 0.7205694
#> 6:  6 1.2836782
#> 7:  7 0.9114737
#> 8:  8 1.4910581
#> 9:  9 0.8722306
#>10: 10 1.1155005
```
