# neovim-python-ide
In this repo, we'll demonstrate how to setup python IDE environment within neovim editor.

# neovim

```sh
$ brew install neovim
$ mkdir -p ~/.config/nvim
$ mkdir -p ~/.vim/plugged
$ cp ./config/nvim/init.vim ~/.config/nvim
```

# node
I used to use nvim to install node.js

```sh
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
$ nvm install node
$ source ~/.bashrc
$ nvm install node
```

# Plug - neovim package manager

```sh
$ curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```


# conda virtualenv
I have used conda to create my own virtualenv already, to find out where is my conda virtualenv directory, please follow the belows:

```sh
$ conda info --envs

# conda environments:
#
base                     /opt/homebrew/Caskroom/miniforge/base
ltv                   *  /opt/homebrew/Caskroom/miniforge/base/envs/ltv

```
as you can see above, the line marked with asterisk is our current active conda virtualenv, we'll use it to configurat `coc.vim` plugin


after finishing `neovim`, `node`, `Plug` and `conda virutalenv` sections, launch nvim as below

```sh
$ nvim
```
and enter into `command line` by issuing `:PlugInstall` to install all needed plugins.

to configure `coc-pyright` plugin, follow the below:

```sh
$ cp config/coc/coc-settings.json ~/.config/coc/
$ cat ~/.config/coc/coc-settings.json
{
    "python.venvPath": "/opt/homebrew/Caskroom/miniforge/base/envs/ltv",
    "python.pythonPath":" /opt/homebrew/Caskroom/miniforge/base/envs/ltv/bin/python3",
    "diagnostic.errorSign":" ✖",
    "diagnostic.warningSign": "!",
    "diagnostic.hintSign":" ▶",
    "diagnostic.virtualText": true,
    "diagnostic.locationlistUpdate": true
}
```







