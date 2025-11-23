# submode.vim

サブモードを追加する Vim プラグインです。

Usage:
------

1. グローバル変数 `g:submode_mappings` にサブモード名とそのサブモードで使用するマッピングを、辞書形式で設定してください
2. サブモードを開始するためのマッピングを設定してください

設定例 :

```vim
" 1. サブモード名とそのサブモードで使用するマッピング
let g:submode_mappings = {
      \   'winsize': {                      " サブモード名
      \     '+': ':resize +1<CR>',          " サブモードで使用するマッピング(`+` キーでウィンドウを縦に拡大)
      \     '-': ':resize -1<CR>',          " サブモードで使用するマッピング(`-` キーでウィンドウを縦に縮小)
      \     '<': ':vertical resize -1<CR>', " サブモードで使用するマッピング(`<` キーでウィンドウを横に縮小)
      \     '>': ':vertical resize +1<CR>', " サブモードで使用するマッピング(`>` キーでウィンドウを横に拡大)
      \   },
      \ }

# 2. サブモードを開始するためのマッピング
nnoremap <C-w>+ :call submode#EnterSubmode('winsize')<Enter>+
nnoremap <C-w>- :call submode#EnterSubmode('winsize')<Enter>-
nnoremap <C-w>< :call submode#EnterSubmode('winsize')<Enter><
nnoremap <C-w>> :call submode#EnterSubmode('winsize')<Enter>>
```

この例では、`winsize` というサブモードを定義し、ウィンドウのサイズ変更用のマッピングを設定しています。
`<C-w>+`、`<C-w>-`、`<C-w><`、`<C-w>>` のいずれかを押すと `winsize` サブモードに入り、それぞれのキーでウィンドウのサイズを変更できます。


License:
--------

Copyright (C) 2025 mikoto2000

This software is released under the MIT License, see LICENSE

このソフトウェアは MIT ライセンスの下で公開されています。 LICENSE を参照してください。


Author:
-------

mikoto2000 <mikoto2000@gmail.com>

