### character型でfunctionを実行する方法
data.tableで新規の列名を追加する際、for文で列名を次々放り込むとき便利

```.R
# Example
eval(parse(text = "1 + 1")) 
# output
#[1] 2

# Example for文
mapping <- data.table(species_id = spIds)
for(cn in regions){
  eval(parse(text = paste0("mapping[,",cn,":=logical()]")))
}

```
