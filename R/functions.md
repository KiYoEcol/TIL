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

### 共通の値を抽出

```.R
v1 <- 1:100
v2 <- 50:200
dplyr::intersect(v1, v2)
#> [1]  50  51  52  53  54  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  72  73  74  75  76  77  78
#> [30]  79  80  81  82  83  84  85  86  87  88  89  90  91  92  93  94  95  96  97  98  99 100
```
