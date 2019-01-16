# pyenv（pythonの複数バージョン管理）
https://qiita.com/crankcube@github/items/15f06b32ec56736fc43a#pyenv%E7%94%A9%E3%81%ABprofile%E3%82%92%E8%AA%BF%E6%95%B4

``
# Home brew で pyenv をインストール
$ brew install pyenv

# よく分からない。。。おまじない
cat << 'EOS' >> ~/.bash_profile
# pyenvさんに~/.pyenvではなく、/usr/loca/var/pyenvを使うようにお願いする
export PYENV_ROOT=/usr/local/var/pyenv

# pyenvさんに自動補完機能を提供してもらう
if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi

EOS
source ~/.bash_profile

# pyenv でインストールできるバージョンを確認
$ pyenv install --list
``

下記のエラーが出た場合

``
zipimport.ZipImportError: can't decompress data; zlib not available
make: *** [install] Error 1
``

以下のコマンドで解決できる。Mac OS Mojaveだとうんたらかんたら

``
sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /
``