### do.callの使いかた
pforeachとの使い分けがイマイチわからん  
do.callの方が速そう

```.R
spIds2 <- do.call("c",lapply(occList,function(x){unique(x$species_id)})) %>% unique() %>% sort()
```

### 参考
- [do.call関数の使いみち - 盆栽日記][1]

[1]:http://d.hatena.ne.jp/dichika/20151213/p1
