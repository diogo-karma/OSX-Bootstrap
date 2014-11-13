#Mac OS X

* [Mensch coding font](http://robey.lag.net/2010/06/21/mensch-font.html)
* [Secrets PrefPane](http://secrets.blacktree.com/)

Apps
----
* [Chrome](http://www.chromium.org/getting-involved/dev-channel)
* [Firefox](http://www.mozilla.org/en-US/firefox/beta/)
* [Oh My ZSH!](http://ohmyz.sh/)
* [Cyberduck](http://cyberduck.io/)
* [Atom](https://atom.io/)
* [Robomongo](http://www.robomongo.org/)


#Xcode Command Line Tools

`Xcode > Preferences > Downloads > Command Line Tools`



#Shell

Install oh-my-zsh
---------------
```bash
curl -L http://install.ohmyz.sh | sh
```

Update .zshrc
-------------
```bash
atom ~/.zshrc
```


```bash
ZSH=$HOME/.oh-my-zsh
plugins=(git osx rails3 ruby github node npm brew)
source $ZSH/oh-my-zsh.sh
export PATH=/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/mysql/bin:/usr/X11/bin
```

# OS X Preferences

```bash
#Use current directory as default search scope in Finder
defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"

#Show Path bar in Finder
defaults write com.apple.finder ShowPathbar -bool true

#Show Status bar in Finder
defaults write com.apple.finder ShowStatusBar -bool true

#Show indicator lights for open applications in the Dock
defaults write com.apple.dock show-process-indicators -bool true

#Enable AirDrop over Ethernet and on unsupported Macs running Lion
defaults write com.apple.NetworkBrowser BrowseAllInterfaces -bool true

#Enable repeat on keydown
defaults write -g ApplePressAndHoldEnabled -bool false

#Set a blazingly fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 0.02

#Set a shorter Delay until key repeat
defaults write NSGlobalDomain InitialKeyRepeat -int 12

#Enable Safari’s debug menu
defaults write com.apple.Safari IncludeInternalDebugMenu -bool true

#Disable the Ping sidebar in iTunes
defaults write com.apple.iTunes disablePingSidebar -bool true

#Add a context menu item for showing the Web Inspector in web views
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

#Show the ~/Library folder
chflags nohidden ~/Library

#Disable ping dropdowns
defaults write com.apple.iTunes hide-ping-dropdown true

```

#Homebrew


```bash
ruby <(curl -fsSkL raw.github.com/mxcl/homebrew/go)
```

```bash
brew update
brew install git ack wget curl redis mongodb node

```

#Git

Setup Github
------------
```bash
ssh-keygen -t rsa -C "dnechtan@gmail.com"

#copy ssh key to github.com
pbcopy < ~/.ssh/id_rsa.pub

#test connection
ssh -T git@github.com

#set git config values
git config --global user.name "Nechtan"
git config --global user.email "dnechtan@gmail.com"
git config --global github.user nechtan

git config --global core.editor "atom"
git config --global color.ui true
```

Install nginx
--------------
```bash
brew install nginx
```

Setup auto start:
```bash
sudo cp -v /usr/local/opt/nginx/*.plist /Library/LaunchDaemons/
sudo chown root:wheel /Library/LaunchDaemons/homebrew.mxcl.nginx.plist
sudo launchctl load /Library/LaunchDaemons/homebrew.mxcl.nginx.plist
```
