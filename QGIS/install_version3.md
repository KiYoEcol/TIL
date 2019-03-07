# QGIS version 3 インストール
でけた！
参考1: https://qiita.com/th1nkd0g/items/3182e210b6a8b0ba0e79  
参考2: https://gis.stackexchange.com/questions/274381/installing-qgis3-on-mac

1. pyenvでpython3.6.*をframework形式でインストール（python 3系以上3.6までしか対応していない2019/01/27現在）

```.sh
$env PYTHON_CONFIGURE_OPTS="--enable-framework CC=clang" pyenv install 3.6.8
```

2. pyenv で　globalに設定

```.sh
$pyenv global 3.6.8
```

3. pyenvでパスの確認

```.sh
$pyenv --version
```

4. pyenvのFrameworkからbrewのFrameworkへ、シンボリックリンクを作成（pyenvのパスが参考1と違くて、だいぶ困った）

```.sh
$sudo ln -s /usr/local/var/pyenv/versions/3.6.8/Python.framework/Versions/3.6 /Library/Frameworks/Python.framework/Versions/3.6
```

5. QGISインストーラを使ってインストール！
