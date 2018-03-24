
=====================================================================
 XMODEM for KOZOS H8/3069F
 Copyright(C) 2012 Shinichiro Nakamura
=====================================================================

 XMODEM for KOZOS H8/3069FはKOZOSブートローダ経由で
 OSを書き込んでいるのだけど、ちょくちょく転送に失敗するので
 作業効率が悪くてモチベーションが下がっている方の為の転送用ツールです。

 /doc
    README.txt          このファイル
 /example
    kozos               動作確認用サンプルデータ
                        KOZOSのブートローダ経由で転送します。
 /src
    Makefile            メイクファイル
    kz_xmodem.c         本体ソースコード
    kz_xmodem.h         本体に対する定義
    serial_linux.c      シリアルポートライブラリの実装(Linux)
    serial_windows.c    シリアルポートライブラリの実装(Windows)
    serial.h            シリアルポートライブラリのインターフェース

=====================================================================
 特徴
=====================================================================

 KOZOSのXMODEM実装に合わせて実装したXMODEM。
 KOZOSのブートローダのloadコマンドを内部で自動発行。
 リセットボタンを押して本プログラムを実行するだけの簡単操作。

=====================================================================
 使い方
=====================================================================

 motファイル名、書き込みインターフェースを与えて実行します。

 例) kz_xmodem kozos /dev/ttyUSB0

 書き込みに成功した場合、実行表示の最後にComplete.と表示されます。

=====================================================================
 出力例
=====================================================================

 (Windows)

  > kz_xmodem.exe kozos com5

    =================================================
    XMODEM for KOZOS H8/3069F (Version 0.0.1)
    Copyright(C) 2012 Shinichiro Nakamura
    =================================================
    Flushing serial port.
    Wait.
    Setup load condition.
    Wait a NAK.
    ..........
    Transmit the target ELF file.
    File(kozos): 24 blocks + 44 bytes
    .........................
    Wait a message from the target.
    Complete.

 (Linux)

  > kz_xmodem kozos /dev/ttyUSB0

    =================================================
     XMODEM for KOZOS H8/3069F (Version 0.0.1)
     Copyright(C) 2012 Shinichiro Nakamura
    =================================================
    Flushing serial port.
    Wait.
    Setup load condition.
    Wait a NAK.
    .........
    Transmit the target ELF file.
    File(kozos): 24 blocks + 44 bytes
    .........................
    Wait a message from the target.
    Complete.

=====================================================================
 バージョン
=====================================================================

 2012/04/28 Version 0.0.1    初版
 2012/04/30 Version 0.0.2    転送サイズの計算バグを修正した。

