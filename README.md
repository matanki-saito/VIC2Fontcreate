# CK2 fontcreate

## Overview

- Steam配信されているWindows版Victoria IIの日本語化パッチの副産物です。パッチはこのプログラムを使って作成されたフォントのみを受け付けます。
- CP1252の0x80から0x9Fまでに相当する文字（例えば€）はUCS2のコードポイントではなくて、CP1252のコードポイントとして作成されます。
- 0x100から0x1FFまでの文字は私用領域(0xE000)にシフトされたコードポイントになります。例えばλは3BBではなくて、0xE3BBのコードポイントになります。

## create on local

### Requirement

- Windows 10 or later
- python 3.5 or later
- pillow ```pip install pillow```

### Usage

1. 同梱している1_tool/bmfont64.exeを使用して、作成したいフォントのconfigurationファイル（.bmfc）を2_main_text/bmfcフォルダに保存してください。この時、含める文字は空にしてください。
1. 含めたい文字を2_main_text/sourceフォルダに任意の名前のBOM付きのUTF-8のtxtファイルに入れておきます。こちらで予めCP1252の追加文字と大体のSHIFT_JISの範囲の文字を入れたテキストを用意していますので、これ以外で必要な文字をtxtとして追加してください。
1. 準備が整ったら、2_main_text/generate.pyを実行します。2_main_text/outフォルダに生成されたフォントが入ります。
1. 3_map_textと4_capital_textについても同様に実施してください。

## Licence

- generate.py : MIT license
- bmfont64.exe : zlib license
- [源ノ明朝](https://github.com/adobe-fonts/source-han-serif) : SIL Open Font License 1.1
- [源ノ角ゴシック](https://github.com/adobe-fonts/source-han-sans) : SIL Open Font License 1.1
- [大正略字フォント](https://booth.pm/ja/items/363104) : SIL Open Font License 1.1
- nvcompress: MIT license
- Add-Font.ps1 : free
