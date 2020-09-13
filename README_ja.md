# くるくるリズム(Twirling rhythm)

「くるくるリズム」は、APL 1.3で動作するリズムゲームのサンプルです。

# ScreenShot

![スクリーンショット](images/rhythm_640.png)

# Features

このコードはAmazon Echo Showシリーズなどに実装されているalexa上で動作します。

APL1.3の新機能、localTimeによる時間取得を駆使し、簡単なリズムゲームを実現しました。

# Requirement

 * Alexaが動作する実機
 * AlexaDeveloperConsoleアカウント
 * 簡単なカスタムスキル作成の知識

# Installation

## 音源の準備（オプション）
本ソースを実行するのに楽曲は必須ではありませんが、画面と音の一致を確認したい場合はライセンスの都合上以下の手順で楽曲を準備する必要があります。

ちなみにマーカーのデータは以下の楽曲をもとに作成しました。
https://dova-s.jp/bgm/play12934.html

mp3をffmpegやWEBツール等でmp4に変換してください。映像部分は表示されませんが、Alexaが正しく読み込むために何らかのダミーの映像または画像と合成してください。

例：music.mp3とdummy.pngからmusic.mp4を作る

```
ffmpeg -loop 1 -r 30000/1001 -i dummy.png -i music.mp3 -c:a copy -c:v libx264 -pix_fmt yuv420p -shortest music.mp4
```

## 開発中スキルとして起動する方法

 * AlexaDeveloperConsoleにてHelloWorldスキルを作成(AlexaHostedSkill)
 * 任意のスキル名を入力
 * 「インターフェース」を押す
 * 「Alexa Presentation Language」を有効にする
 * 「インターフェースを保存」
 * 「対話モデル」→「JSONエディター」画面へ
 * /interactionModels/custom/ja-JP.json をコピーペースト
 * 「モデルを保存」して「モデルをビルド」する
 * コードエディタ画面へ
 * lambda配下のファイルをすべてコピーペースト
 * /lambda/apl/rolling.json の445行目を実際のファイルに差し替える
 * 保存してデプロイ
 * 「テスト」画面へ
 * プルダウンの「非公開」を「開発中」に

## APLエディタ上で実行する方法

 * AlexaDeveloperConsoleにてHelloWorldスキルを作成(AlexaHostedSkill)
 * 適当にスキル名を入力
 * 「ビルド」画面にて、「マルチモーダル」画面へ
 * 「Visual」を押して「Create Visual Response」
 * 「コードをアップロード」
 * "aplEditor/apl_template_export.json"を読み込み
 * 画面右上の「テンプレートを保存」を押す

# Usage

## 開発中スキルとして起動する方法

実機から「アレクサ、＊＊＊を開いて」で起動
（PCのシミュレータでは画面と音がずれます）

## APLエディタ上で実行する方法

APLエディタ画面にて、出力シミュレーションの下の実機出力ボタンを押す
（PCのシミュレータでは画面と音がずれます）

## 遊び方

マーカー（カプセル）が円の左端に来た時にPUSHボタンを押すと、マーカーが消えて得点が入ります。

# Note
2020年9月時点では動作確認済みです。今後の仕様変更等により正常に動作しなくなった場合、その動作は保証しませんのでご注意ください。

# Author

* kyukkyu
* Twitter : https://twitter.com/Synoyan

# License

"くるくるリズム(Twirling rhythm)" is under [MIT license](https://en.wikipedia.org/wiki/MIT_License).

