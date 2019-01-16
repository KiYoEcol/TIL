# pyenv による　python　のバージョン切り替え
https://qiita.com/twipg/items/75fc9428e4c33ed429c0

切り替えられるバージョンの確認

```shell
% pyenv versions  
  system  
  2.7.10  
* 3.5.0 (set by /Users/xxx/.pyenv/version)  
```

バージョン切り替え
globalとすると全体に、localにするとそのカレントディレクトリに指定したバージョンが反映されます。

```shell
$ pyenv global 3.5.0
$ python --version
Python 3.5.0

$ pyenv local 2.7.10
$ python --version
Python 2.7.10
```
