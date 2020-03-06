# neovim-init-vim
Personal customized init.vim for [Neovim](https://neovim.io/).

Set the alias vim to execute Neovim:

    echo 'alias vim="nvim"' >> ~/.bashrc

Make sure the Vim-plug Plugin Manager is installed:

    curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \
        https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

Create a file init.vim in ~/.config/nvim:

    mkdir -p ~/.config/nvim/
    vim ~/.config/nvim/init.vim

Copy the content to ~/.config/nvim/init.vim
````
"============================================================
" Plugins
"============================================================
call plug#begin()
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
