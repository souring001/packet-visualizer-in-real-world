# packet-visualizer-in-real-world
LANケーブルに流れるパケットをLEDテープで可視化する

## LANケーブルを流れるPacketのプロトコルを判別

利用ツール　「tsark」
tsarkとはwiresharkのCUIツール　流れるパケットを監視可能

tsharkでは
 `tshark -i 1 -w packet`
 で採取したパケットをフォルダに吐くことが可能。あとはOS側で単位時間当たりにどのプロトコルがどれだけ流れているか把握できるプログラムを書いて、LEDテープへプロトコルに対応した信号を渡す。

参考サイト；[tshark使い方まとめ](https://oxynotes.com/?p=7969)

利用ツール　「tcpdump」

 `sudo tcpdump -nn -t`
 行毎の先頭に「プロトコル名」が出る
 
 
