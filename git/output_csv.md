# git log を csv ファイルへ出力
https://qiita.com/iskou9821/items/0065cfd44c229cb74a83

```
git --no-pager log --since=2017-03-01  --until=2017-03-31 --pretty=format:"\"%ad\",\"%h\",\"%an\",\"%s\"" --date=short --no-merges --all --date-order > commits.csv
```
