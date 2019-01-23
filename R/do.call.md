### do.callの使いかた
pforeachとの使い分けがイマイチわからん

```.R
spIds2 <- do.call("c",lapply(occList,function(x){unique(x$species_id)})) %>% unique() %>% sort()
```

- [参考1][1]
[1]:http://d.hatena.ne.jp/dichika/20151213/p1
