# TL Split Keyboard 18mm Rev1ビルドガイド

TL Split Keyboard 18mmは、TRONキーボード風のキーボードです。

## 説明
TL Split Keyboard 18mmは、PCBが左右違います。4.7kΩ抵抗（R1,R2）がある方が左です。
基本的に、左側にUSBケーブルを接続するようにしています。

PCBには、表面と裏面があります。"TL Split Keyboard"と記載がある方が、表面です。

## 組み立て
### PCBへパーツ半田付け

- ダイオードを、左右PCB表面に36カ所実装します。

ダイオードを、左右PCB表面に実装します。

ダイオードは、穴の長さに合わせて予め折り曲げておくと、半田付けしやすいです。

![ダイオード](./diode.jpg)

ダイオードは極性があるので、カソード（黒い方）をシルク印刷で線が入っている方（かつKと書かれて、穴が四角の方）にします。

![ダイオード半田付け](./diode2.jpg)

ダイオードは、マスキングテープで固定しておくと、半田付けしやすくなります。

![ダイオード半田付け](./diode3.jpg)

- 4.7kΩ抵抗を左側PCB表面に2カ所実装します。

4.7kΩ抵抗を、左側PCB表面に実装します。極性は無いので、どちらでもかまいません。

![抵抗半田付け](./resistor2.jpg)


- リセットスイッチを、左右PCB裏面に実装します。

リセットスイッチを、左右PCB裏面に実装します。左右PCBに、それぞれ実装してください。

![リセットスイッチ](./board.jpg)

※裏面にシルク印刷されています。

- TRRSジャックを、左右PCB裏面に実装します。

TRRSジャックを、左右PCB裏面に実装します。左右PCBに、それぞれ実装してください。

![TRRSジャック](./trrs.jpg)

半田付けする際には、スイッチにマスキングテープを貼っておくと、半田付けしやすいです。

![TRRSジャック半田付け(./trrs2.jpg)

※裏面にシルク印刷されています。

### Pro Microへコンスルー半田付け

遊舎工房で購入すれば、コンスルー付きが買えます。

PCBから外した状態で、部品（USBコネクタなど）が実装されている面にコンスルーを載せて、半田付けします。

できたら、左右PCBの裏面にはめ込みます。基板の外側（左側は左、右側は右）にUSBコネクタが来るようにはめます。

### キースイッチ半田付け

アクリルのトッププレートとPCBの間にスペーサー(3mm)をはさみ、左右それぞれ4カ所ネジ止めします。ねじ頭が上側に来るようにして、PCBの下にはスペーサー(10mm)で止めてください。
キースイッチをアクリルトッププレートの上からアクリル・PCBにはめ込み、実装します。ここでキーが浮かないよう、しっかりトッププレートにはめ込んで、半田付けしてください。

## ファームウェア書き込み
[QMK Toolbox](https://github.com/qmk/qmk_toolbox) で、ファームウェア（hexファイル）をProMicroに書き込む必要があります。

[QMK Toolbox](https://github.com/qmk/qmk_toolbox) のインストール・使い方については、サリチル酸さんが書かれた[（初心者編）自作キーボードにファームウェアを書き込む](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox) が分かりやすいです。

TL Split Keyboard 18mmmと16mmはファームウェアが共通なので、 [tlsplit18_default.hex](https://github.com/satromi/tlsplit18_rev1/blob/master/tlsplit18_default.hex) をダウンロードしてQMK Toolboxで書き込みます。

ファームウェアは、左右のProMicroそれぞれに書き込む必要があります。

他のキーマップに変更したい場合は、VIA対応ファームウェアも準備しています。[tlsplit18_via.hex](https://github.com/satromi/tlsplit18_rev1/blob/master/tlsplit18_via.hex) をダウンロードして、QMK Toolboxで書き込みます。

VIA対応ファームウェアの場合、Webサイトからキーマップを変更できる [REMAP](https://remap-keys.app/)  も利用できます。
[REMAPのTL Split Keyboardページ](https://remap-keys.app/catalog/AqZy7RsTgu0kxObJxxYr)  から書き換えてみてください。

## 動作確認

左右のキーボードをTRRSケーブルで繋いだら、USBケーブルでPCと接続し、動作確認してください。
