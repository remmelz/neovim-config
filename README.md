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

## Configure

  cd ~/.config
  git clone https://github.com/remmelz/neovim-config.git
  ln -s neovim-config nvim


## Install Plugins
In the editor, execute PlugInstall to download and install the plugins:

    :PlugInstall



