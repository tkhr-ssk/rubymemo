# rubymemo
just private memo of ruby

## 基本
- インクリメント、デクリメント演算子がない。<br>
http://blade.nagaokaut.ac.jp/cgi-bin/scat.rb/ruby/ruby-list/5323 <br>
http://blog.tokoyax.com/entry/ruby/increment <br>

## Rdoc
- https://github.com/rdoc/rdoc
- http://docs.seattlerb.org/rdoc/
- http://ruby.gfd-dennou.org/tutorial/rdoc/

## ocra
ruby環境丸ごとWindowsのexe化するライブラリ
下記でインストール
```
> gem install ocra
```
下記でexeがつくれる。
```
> ocra sample.rb
```
https://github.com/larsch/ocra


## 範囲オブジェクト .. ...
0..10 -> 0から10のRangeオブジェクト

## 繰り返し
- breakとnext

### loop (Kernelクラス メソッド)
```
n=0
loop {
  p n+=1
  break if 10<n
}
```
breakするまでループ

### each
```
(0..1000).each {|i|
 p i
}
```
- 変数 ```|i|``` はなくてもOK
- ```p```は、引数のオブジェクトを分かりやすい文字列にして標準出力に出力。

### times

