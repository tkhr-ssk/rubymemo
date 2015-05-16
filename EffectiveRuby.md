#item 3 Perl風機能を避ける

```
def extract_error(message)
  if message=~ /^ERROR:\s+(.+)$/
    $1
  else
    "no error"
  end
end
```

```
def extract_error(message)
  if m = message.match(/^ERROR:\s+(.+)$/)
    m[1]
  else
    "no error"
  end
end
```
- `~=`や`$1`の代わりに`match`を使う。

株式会社翔泳社「Effective　Ruby あなたのRubyをより輝かせる 48の特別な方法」より引用
