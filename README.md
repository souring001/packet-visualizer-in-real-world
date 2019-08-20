# packet-visualizer-in-real-world
LANケーブルに流れるパケットをLEDテープで可視化する

## LANケーブルを流れるPacketのプロトコルを判別

~利用ツール　「tsark」~
~tsarkとはwiresharkのCUIツール　流れるパケットを監視可能~

~tsharkでは~
~ `tshark -i 1 -w packet`~
~で採取したパケットをフォルダに吐くことが可能。あとはOS側で単位時間当たりにどのプロトコルがどれだけ流れているか把握できるプログラムを書いて、LEDテープへプロトコルに対応した信号を渡す~

~参考サイト；[tshark使い方まとめ](https://oxynotes.com/?p=7969)~

**利用ツール　「tcpdump」**

 `sudo tcpdump -nn -t`
 行毎の先頭に「プロトコル名」が出る
 
 <img width="197" alt="スクリーンショット 2019-08-20 20 40 40" src="https://user-images.githubusercontent.com/32484108/63344578-ba00dd00-c38b-11e9-9127-1ec5e1a2c73a.png">

ファイルに書き込んでgolang側で一列目を抜けば良い

## デモで特定のプロトコルの通信を行う

**TCP** `nc [IPアドレス][ポート番号]`

**IP**  `nc -u [IPアドレス][ポート番号]`

**ICMP** `ping [IPアドレス]`

