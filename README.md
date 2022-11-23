# unix-command-study
I am studying unix command now.

## ランダム文字列生成
- `cat /dev/urandom | LC_CTYPE=C tr -dc 'a-zA-Z0-9' | fold -w 16 | head -n 32 | sort uniq`
- `cat /dev/urandom | LC_CTYPE=C tr -dc 'A-Z0-9' | fold -w 4 | head -n 1000 | sort > a.txt`



