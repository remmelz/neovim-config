# neovim-ide-config
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

## Configure

    cd ~/.config
    git clone https://github.com/remmelz/neovim-config.git
    ln -s neovim-config nvim


## Install Plugins
In the editor, execute PlugInstall to download and install the plugins:

    :PlugInstall

## Shortcuts
Overview of the keyboard shortcuts:

```
nnoremap <F1> :tabnext<enter>
nnoremap <F5> :DevelopMode<enter>
nnoremap <F6> :NewTab<enter>
nnoremap <F2> :GotoFiletree<enter>
nnoremap <F3> :GotoTerminal<enter>
nnoremap <F4> :GotoEditor<enter>
nnoremap <F10> :ExitNeovim<enter>

nnoremap <A-n> :tabnext<enter>
nnoremap <A-h> :GotoFiletree<enter>
nnoremap <A-j> :GotoTerminal<enter>
nnoremap <A-k> :GotoEditor<enter>

imap ` <Esc>
```


