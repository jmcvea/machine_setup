# machine_setup
Files to document and automate the setup and customization of a new Mac/Linux system

## Shell
I like to use zsh with the prezto config system.  See the [https://github.com/jmcvea/prezto] repository

## Directory setup
```
cd ~
mkdir Code
```
## Brew setup
```script
# install brew.  See (http://brew.sh).
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew tap caskroom/cask
brew tap homebrew/completions
brew tap homebrew/versions
brew tap pivotal/tap
brew install ant bash-completion brew-cask cloudfoundry-cli cmake docker-completion git jq nave rbenv readline the_silver_searcher tig tmux tree vim wget
brew cask install iterm dockertoolbox
```

## Coding
### Fonts
Install the Powerline fonts
```script
cd ~/Code
git clone https://github.com/powerline/fonts.git
~/Code/fonts/install.sh
```

### VIM
_TBD_ - use mutewinter with customization.  Requires vim 7.4 or higher.  The YouCompleteMe plugin requires cmake.  Install vim and cmake from brew to get the latest.
```script
brew install vim cmake
git clone http://github.com/mutewinter/dot_vim.git ~/.vim
cd ~/.vim
scripts/setup
~/.vim/bundle/YouCompleteMe/install.sh
```


### Sublime Text
Configuration files
* Preferences.sublime-settings
* Package Control.sublime-settings
  * _TBD_ - document setup and automate.  See miohtama/sublime-helper for inspiration

### iTerm2
* TBD - document Preferences settings
  * Turn on the `View > Show Tabs in Fullscreen` option
  * Set up iTerm2 to show man pages
    1. In prefs->profiles->(your profile)->advanced click "edit" under Smart Selection.
    2. Select the first item, "word bounded by whitespace"
    3. Click "Edit Actions..." below the table.
       * A panel opens. Click the [+] button to add a new action. (these actions are added to the context menu when you right click on a word)
    4. Double click on the first cell to set the title to "Open Man Page"
    5. Set the action to "Open URL..."
    6. Double click on the third cell to set the URL to "x-man-page://\0" (not including quotes, of course)
    7. Create a new profile
    8. Name it "Man Page Viewer"
    9. Set its command to /usr/bin/man $$HOST$$
    10. Select "x-man-page" under "Schemes Handled"
