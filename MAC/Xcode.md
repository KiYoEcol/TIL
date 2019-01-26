### iPhoneシミュレータの動画キャプチャ
シュミレータを起動した上で下記を実行。 Ctrl + c で撮影終了。

```
xcrun simctl io booted recordVideo videoName.mov
```

xcrun simctl コマンドが使えない場合
Xcode > Preferences > Locations でXcodeのバージョンを選択する
