# Ubuntu Setup

## Config
### Keyboard
* as [here](http://www.howtogeek.com/194705/how-to-disable-or-reassign-the-caps-lock-key-on-any-operating-system/)
* add startup (vai 'Start' tool) to run
```shell
set xkbmap -option caps:escape
```
* note old method (fails on tmux):
 * file : /etc/default/keyboard
  * `XKOPTIONS="caps:escape"`
  * then:
```shell
sudo dpkg-reconfigure keyboard-configuration
```
### Network share
```shell
sudo mount /media/hub
sudo apt-get install cifs-utils
sudo vim /etc/fstab
 >> then: 
 //192.168.1.254/public /media/hub cifs username=admin,password=newrouterpwd,iocharset=utf8,sec=ntlm 0 0 
sudo mount -a
```


### Unity Tweak Tool
```shell
sudo apt-get install unity-tweak-tool gnome-tweak-tool
```

### Firewall
```shell
sudo ufw enable
```

### System Load Indicator
* from [here](http://www.howtogeek.com/118908/10-awesome-indicator-applets-for-ubuntus-unity-desktop/)
```shell
sudo apt-get install indicator-multiload
```

### Network Speed Panel
* from [here](http://tipsonubuntu.com/2015/08/19/network-speed-on-panel/)
```shell
sudo add-apt-repository ppa:fixnix/netspeed
sudo apt-get update
sudo apt-get install indicator-netspeed-unity
```

## Wine
* following instructions from [here](https://wiki.winehq.org/Ubuntu)
* then setup drive with `winecfg`
### TheBat
* Double-click v5.x installer [here](https://www.ritlabs.com/en/products/thebat/archive_version.php)
* TODO : find registration key!

## Unity Tweak Tool
* as you wish

## BleachBit
* from software
* (todo - run this)

## FileZilla
* from software

## LilyTerminal
* install via software centre
* configuration a complete pain
 * file: /etc/xdg/lilyterm.conf
```shell
fullscreen = 1
background_color = #000000
rgba = 0
scroll-lines = -1

```
 * file: /usr/share/applications/lilyterm.desktop
```shell
exec=lilyterm -u /etc/xdg/lilyterm.conf
```

## bash
* add .bash_aliases from /reference/bash

## tmux
* install:
```shell
sudo apt-get install tmux
```
* configure:
 * file: ~/.tmux.conf
```shell
set-window-option -g windown-status-current-bg yellow
set -g mouse on

bind W source-file ~/.tmux/new-window-3-pane
```
 * files: ~/.tmux/new-window-3-pane
```shell
neww -n foo
split -h
split -v
selectp -L
```

## vim
* initial install
```shell
sudo apt-get install vim
```
### vundle
* install from [GitHub](https://github.com/VundleVim/Vundle.vim)
* plugins:
```shell
Plugin 'VundleVim/Vundle.vim'
Plugin 'scrooloose/syntastic'
Plugin 'Valloric/YouCompleteMe'
```

#### YouCompleteMe plugin
* requires building for [JavaScript support](https://github.com/Valloric/YouCompleteMe#ubuntu-linux-x64)
```shell
sudo apt-get install build-essential cmake
sudo apt-get install python-dev python3-dev
cd ~/.vim/bundle/YouCompleteMe
./install.py --tern-completer
```

#### Tern configuration:
* add `.tern-project` file with content [defined here](http://ternjs.net/doc/manual.html#configuration)

## Firefox
* installed by defaut
* Add-ons:
 * lastpass
 * uBlock Origin

## Chrome for Linux
* **not chromum**
* download from Google
* run direct so go through setup launcher (error when running dpkg -i X.deb)
* Extensions (note: sync'd on sign-in):
 * lasspass
 * uBlock Origin
 * Markdown Preview Plus
 * Adblock for Youtube
* also added symbloic link on `/usr/bin` so can fire with `chrome` command

## Git
* install
```shell
sudo apt-get install git
```
* configure
 * file: ~/.gitconfig
```shell
[user]
	name = Mike Evans
	email = mike.evans@numical.com

[credential]
        helper = cache --timeout=28800

[alias]
        co = checkout
        cm = commit
        st = status
        br = branch
        hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short 

[core]
	editor = vim
```
* tools
```shell
sudo apt-get install meld
```

## Node / NPM
* install
* TODO
* global modules
 * note NVM via install script from https://nvm.sh
```shell
sudo npm i -g semistandard node-inspector http-server typescript available-versions
```




