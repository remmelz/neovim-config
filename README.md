# neovim-init-vim
Personal customized init.vim for [Neovim](https://neovim.io/).

Set the alias vim to execute Neovim:
```
echo 'alias vim="nvim"' >> ~/.bash_profile
```

Make sure the Vim-plug Plugin Manager is installed:
```
curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \
   https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Copy the content to ~/.config/nvim/init.vim
````
"============================================================
" Plugins
"============================================================
call plug#begin()
Plug 'dart-lang/dart-vim-plugin'
call plug#end()

"============================================================
" GVIM Settings
"============================================================
"set guifont=Lucida_Console:h10:cANSI:qDRAFT
"set lines=55 columns=150
"set guioptions-=T
"set clipboard=unnamed
"
"colorscheme slate

"============================================================
" General
"============================================================
set tabstop=4        " The width of a TAB is set to 4.
set shiftwidth=4     " Indents will have a width of 4.
set softtabstop=4    " Sets the number of columns for a TAB.
set expandtab        " Expand TABs to spaces.
set nowrap           " do not automatically wrap on load
set formatoptions-=t " do not automatically wrap text when typing
set nu               " Sets linenumbers
set list
set mouse+=a

"============================================================
" Vimwiki
"============================================================
let wiki_1                  = {}
let wiki_1.path             = '~/Stack/Wiki'
let wiki_1.template_path    = '~/Stack/Wiki/templates'
let wiki_1.template_default = 'default'
let wiki_1.template_ext     = '.html'
let wiki_1.ext              = '.wiki'
let g:vimwiki_list          = [wiki_1]
let g:vimwiki_use_mouse     = 1

"============================================================
" File explorer
"============================================================
let g:netrw_banner       = 0
let g:netrw_winsize      = 25
let g:netrw_liststyle    = 3
let g:netrw_browse_split = 4

"============================================================
" Shortcuts
"============================================================
nnoremap <C-E> :Vexplore<enter>
nnoremap <C-F> :VimwikiSearch<space>/\c
nnoremap <C-T> :VimwikiSearchTag<space>
nnoremap <C-N> :lnext<enter>

"============================================================
" Remove empty spaces and repace tabs
"============================================================
function! RemoveTabSpaces()
    :%s/        /    /g
    :%s/ *$//g
    :nohlsearch
endfunction

command RemoveTabSpaces :call RemoveTabSpaces()

"============================================================
" Highlight color
"============================================================
highlight VimwikiHeader1 ctermfg=27
highlight VimwikiHeader2 ctermfg=27
highlight VimwikiPre ctermfg=68
highlight LineNr ctermfg=grey

````
