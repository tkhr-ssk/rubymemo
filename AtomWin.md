# Atom for Windows

AtomのWindows版に特化したネタ。
Mac版の記事が多いので要注意。

まずは、公式インストール

https://atom.io/

※chocolateyだと古いバージョンが入ったりするので、公式がよさそうです。

## Proxy

```
> apm config set https-proxy http://proxy-server.example.com:8080
```

- [ATOMエディタのproxy設定](http://qiita.com/tsukamoto/items/cef0f2d7e2b33a26a9e5)

## Package

- japanese-menu
- japanese-wrap

### インストール済みパッケージ一覧出力

```
> apm ls
```

## Setting

- Config

```
welcome:
  showOnStartup: false
core:
  themes: [
    "atom-light-ui"
    "solarized-dark-syntax"
  ]
  destroyEmptyPanes: false
editor:
  invisibles: {}
  fontFamily: "Meiryo UI"
  showInvisibles: true
  showIndentGuide: true
"git-diff":
  showIconsInEditorGutter: true
```

- StyleSheet

```
@font-family: "Helvetica Neue", Helvetica, Arial, "游ゴシック", YuGothic, "ヒラギノ角ゴ ProN W3", "Hiragino Kaku Gothic ProN", "メイリオ", Meiryo, sans-serif;
.markdown-preview {
  margin: 0;
  font-family: @font-family;
  font-size: 16px;
  color: #4a4a4a;

  h1, h2, h3, h4, h5, h6 {
    font-family: @font-family;
  }
}
```

- Keymap

```
'atom-text-editor':
  'f12': 'symbols-view:go-to-declaration'
  'shift-f12': 'symbols-view:return-from-declaration'
```

## Shortcut

- Ctrl + r ファイル内シンボル検索
- Ctrl + Shift + r プロジェクト全体シンボル検索(ctags)
- Ctrl + Shift + p コマンドパレットを開く

## Ctags関連

- [Atomのctags (Symbols View)について](http://tkhrssk.hatenablog.com/entry/2015/07/05/201809)
