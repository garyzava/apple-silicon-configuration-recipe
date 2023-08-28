# Apple Silicon Configuration Recipe For Data Engineers

Basic configuration commands to have your Mac up and running for Data Engineering activities.

<br />

<hr />

## Overview

* [Python3](#python3)
* [XCode](#xcode)
* [Homebrew](#homebrew)
* [Anaconda](#anaconda)

<br />

<hr />

## Python3
* Download the .pkg installer from python.org [here](https://www.python.org/downloads/) 

<br />

<hr />

## XCode

Best way to install XCode might not necessarily be through the App Store
* Log in and download XCode installer [here](https://developer.apple.com/download/all/?q=xcode)
* Open terminal and go to the Download folder
* `xip -x <file_name.xip> ` Bypass verification step when unzipping
* On Finder go to the 'Applications' and remove any previous XCode app and just drag and drop from 'Downloads' to 'Applications'

<br />

<hr />

## Homebrew

* `xcode-select --install` Install CLT (Command Line Tools) before installing Homebrew
* Download the new .pkg installer [here](https://github.com/Homebrew/brew/releases/latest)
* Add Homebrew to your PATH run brew shellenv in your shell profile (e.g. ~/.bash_profile or ~/.zprofile)
* `echo "export PATH=/opt/homebrew/bin:$PATH" >> ~/.bash_profile && source ~/.bash_profile` Update the PATH and activate it

<br />

<hr />

## Bash or Zsh

### Background
* When opening terminal, there's a message to switch to Zsh: `The default interactive shell is now zsh. To update your account to use zsh, please run 'chsh -s /bin/zsh'. For more details, please visit https://support.apple.com/kb/HT208050`
* .bash_profile vs. .zprofile: If you have environment variables or startup commands in .bash_profile, you may want to move them to .zprofile. zsh will not automatically source .bash_profile, so any settings or configurations there won't be applied in a zsh session.
* .bashrc vs. .zshrc: The .bashrc file is for interactive bash sessions. In zsh, the equivalent is .zshrc. If you have aliases, functions, or other configurations in .bashrc, you might want to transfer them to .zshrc.
* However in OSX, ALL interactive shells are login shells hence many people do not create bashrc or zshrc.

### Migrate (optional)
* `chsh -s /bin/zsh` Change from Bash to Zsh
* `nano ~/.zprofile` Open the .zprofile file, it will empty if it didn't exist previously
* `if [ -f ~/.bash_profile ]; then . ~/.bash_profile; fi` Add at the very bottom of the file ~/.zprofile. Everytime a Zsh session starts, it will run the bash_profile file.

### Reference:

* https://stackoverflow.com/questions/23233603/how-to-load-bash-profile-when-entering-bash-from-within-zsh
* https://carlosroso.com/the-right-way-to-migrate-your-bash-profile-to-zsh/

<br />

<hr />

## Git

* `brew install git` Install Git using Homebrew

<br />

<hr />

## Anaconda

* Download the pkg installer for Mac M1/M2 [here](https://www.anaconda.com/)
* `conda config --set auto_activate_base false` Use the system environment without conda as the default. This is remove (base) from terminal prompt after updating conda

### Refereces:
* Machine Learning test https://www.youtube.com/watch?v=_1CaUOHhI6U and https://github.com/mrdbourke/m1-machine-learning-test
* To do: https://c51.lbl.gov/~walkloud/work_home/personal/setting-up-my-mac/homebrew
