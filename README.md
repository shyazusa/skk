# skk dictionary

ほぼほぼ個人用のskk辞書まとめです。  
名言やら普段よく使用するものが詰まっています。

## URL指定で辞書を使う

[https://raw.githubusercontent.com/shyazusa/skk/master/SKK](https://raw.githubusercontent.com/shyazusa/skk/master/SKK)  
これを指定して下さい。

多分読み込めるハズ……  

- SKK日本語入力FEP (Windows)
- ~~AquaSKK (Mac)~~
- FlickSKK (iPhone)

で確認。

※AquaSKKは辞書の「場所」にURLが指定できなくなっていたので、このリポジトリをCloneしてローカルのファイルを指定して下さい。

## 辞書の内容

[skk/SKK.txt at master · shyazusa/skk](https://github.com/shyazusa/skk/blob/master/SKK.txt)

## 辞書編集方法

### 各種インストール

```
nkf
$ brew install nkf

glib2
$ brew install glib

skktools
$ git clone skk-dev/skktools /tmp/skktools && cd /tmp/skktools && ./configure && make && make install && cd -
```

### 編集

1. SKK.txtに辞書を追加/編集/削除
1. `$ nkf -e SKK.txt > SKK.euc`
1. `$ rm -f SKK`
1. `$ skkdic-expr2 SKK.euc > SKK`
1. `$ rm -f SKK.euc`
1. `$ rm -f SKK.txt`
1. `$ nkf -w SKK > SKK.txt`
1. 中身を確認する

### ワンライナー

```
$ nkf -e SKK.txt > SKK.euc && rm -f SKK && skkdic-expr2 SKK.euc > SKK && rm -f SKK.euc && rm -f SKK.txt && nkf -w SKK > SKK.txt
```
