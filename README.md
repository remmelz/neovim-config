# neovim-init-vim
[Neovim](https://neovim.io/) is a fork of Vim aiming to improve user experience, 
plugins, and GUIs. This is a personal customized init.vim

## Requirements
Set the alias vim to execute Neovim:

    echo 'alias vim="nvim"' >> ~/.bashrc

Make sure the Vim-plug Plugin Manager is installed:

    curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \
        https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

Create a file init.vim in ~/.config/nvim:

    mkdir -p ~/.config/nvim/

Install NodeJS for COC Codecompletion:

    zypper -n in nodejs10

## Configuration
Copy the content to ~/.config/nvim/init.vim
````

"============================================================
" Plugins
"============================================================
call plug#begin()
  Plug 'neoclide/coc.nvim', {'branch': 'release'}
  Plug 'dart-lang/dart-vim-plugin'
  Plug 'scrooloose/nerdtree'
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
set tabstop=2        " The width of a TAB is set to 4.
set shiftwidth=2     " Indents will have a width of 4.
set softtabstop=2    " Sets the number of columns for a TAB.
set expandtab        " Expand TABs to spaces.
set nowrap           " do not automatically wrap on load
set formatoptions-=t " do not automatically wrap text when typing
set nu               " Sets linenumbers
set list
set mouse+=a

"============================================================
" Coc is an intellisense engine for Vim/Neovim.
"============================================================

" Use tab for trigger completion with characters ahead and navigate.
" NOTE: Use command ':verbose imap <tab>' to make sure tab is not mapped by
" other plugin before putting this into your config.
inoremap <silent><expr> <TAB>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<TAB>" :
      \ coc#refresh()
inoremap <expr><S-TAB> pumvisible() ? "\<C-p>" : "\<C-h>"

function! s:check_back_space() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction

"============================================================
" NERDtree
"============================================================

function! SideExplorer()
  :let g:NERDTreeMinimalUI = 1
  :let g:NERDTreeDirArrows = 1
  :let g:NERDTreeWinSize=40
  :NERDTreeToggle
endfunction

command SideExplorer :call SideExplorer()

nnoremap <C-E> :SideExplorer<enter>

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
highlight LineNr ctermfg=grey
````
