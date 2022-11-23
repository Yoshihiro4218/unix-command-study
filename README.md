# unix-command-study
I am studying unix command now.

## ランダム文字列生成
- `cat /dev/urandom | LC_CTYPE=C tr -dc 'a-zA-Z0-9' | fold -w 16 | head -n 32 | sort uniq`
- `cat /dev/urandom | LC_CTYPE=C tr -dc 'A-Z0-9' | fold -w 4 | head -n 1000 | sort > a.txt`
- `cat /dev/urandom | LC_CTYPE=C tr -dc '0-9' | fold -w 4 | head -n 1000 | sort > num.txt`

## 2ファイル結合
- `paste -d _ a.txt num.txt > a_with_num.txt`

## カット
- `cut -d '_' -f 1,3 a_and_b_with_num.txt`

## 行数確認
- `cat a.txt | grep wc -l`

## ソート
- `a.txt | sort`

### option
- `-n` データを文字ではなく、数値として並び変える
- `-r` 降順にデータを並び変える
- `-u` 重複を排除して並び変える
- `-f` 大文字と小文字を区別なく並び変える
- `-b` 先頭に挿入されている空白を無視して並び変える
- `-k` キーを指定して並び変える（下記「-t」と併用）
- `-t` 区切りの文字を指定する（下記「-k」と併用）

## uniq
- `uniq -c a.txt`
- `uniq -c num.txt | sort -nr | head`

## ソート済みのテキストファイルを比較
- `comm a.txt b.txt`

### option
- `-1` 1列目（ファイル1のみに含まれる行）を出力しない
- `-2` 2列目（ファイル2のみに含まれる行）を出力しない
- `-3` 3列目（両方のファイルに含まれる行）を出力しない

## perl 使用
- `cat a.txt | perl isOnlyAtoK.pl | head`
- `cat num.txt| perl isFiveDivisible.pl| head`

```
use strict;
use warnings;

while(<>){
  if($_ % 5 == 0) {
   print
  }
}

```

### ワンライナー 
- 例) `cat a.txt | perl -ne 'print if !/[0-9]/' | head`
  - 数字を使用していない行




