# Environment settings

# Mac OS

## Homebrew

The missing package manager for macOS
```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## iTerm2

iTerm is is a customisable terminal for mac.
```sh
brew cask install iterm2
```
Da bi strelice i delete i sl. radilo kao sa textom: __iTerm → Preferences → Profiles → Keys → Load Preset... → Natural Text Editing__

## Zsh

Zsh je zamena za bash i vec je preinstaliram na mac-u ali je mnogo starija verzija.
```sh
brew install zsh
```

Sledeca komanda postavlja zsh kao podrazumevani shell
```sh
chsh -s /bin/zsh
```

Sva podesavanja za zsh se rade u `~/.zshrc`. To je fajl koji se ucitava pri svakom pokretanju terminala.

```sh
brew install zsh-syntax-highlighting zsh-autosuggestions
```

### Fontovi za terminal
Da bi se prikazivali simboli i ikonice i terminalu treba instalirati posebne fontove kao npr __Nerd Font__
```sh
brew tap caskroom/fonts
brew cask install font-hack-nerd-font
```
U __iTerm2 -> Preferences -> Profiles -> Text -> Font -> Change Font__ izabrati __Hack Regular Nerd Font__ i odgovarajucu velicinu, npr __14__ , aktivirati __Use a different font for non-ASCII text__ i tu izabrati isti font i velicinu.
### Powerlevel9k i kolor tema za Zsh i Terminal
Na sajtu [https://iterm2colorschemes.com](iterm2colorschemes.com) ima puno kolor tema za iTerm i drugo.

Prvo `echo "POWERLEVEL9K_MODE='nerdfont-complete'" >> ~/.zshrc` pa tek onda instalacija teme zbog pravilne inicijalizacije.

```sh
cd ~
git clone https://github.com/bhilburn/powerlevel9k.git ~/powerlevel9k
mv ~/powerlevel9k ~/.powerlevel9k
```

Editovati `~/.zshrc` tako da izgleda ovako:
```sh
# Load Nerd Fonts with Powerlevel9k theme for Zsh
POWERLEVEL9K_MODE='nerdfont-complete'
source ~/.powerlevel9k/powerlevel9k.zsh-theme

# Load Zsh tools for syntax highlighting and autosuggestions
HOMEBREW_FOLDER="/usr/local/share"
source "$HOMEBREW_FOLDER/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh"
source "$HOMEBREW_FOLDER/zsh-autosuggestions/zsh-autosuggestions.zsh"
```

Opciono mogu se dodati stvari kao sto je scledece:
```sh
# JavaScript Prompt
POWERLEVEL9K_CUSTOM_JAVASCRIPT="echo -n '\ue781' JavaScript"
POWERLEVEL9K_CUSTOM_JAVASCRIPT_FOREGROUND="black"
POWERLEVEL9K_CUSTOM_JAVASCRIPT_BACKGROUND="yellow"

# Python prompt
POWERLEVEL9K_CUSTOM_PYTHON="echo -n '\uf81f' Python"
POWERLEVEL9K_CUSTOM_PYTHON_FOREGROUND="black"
POWERLEVEL9K_CUSTOM_PYTHON_BACKGROUND="blue"

# Customise the Powerlevel9k prompts
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(ssh dir vcs newline status)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=()
POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
```

## NVM - Node Version Controll
```sh
brew install nvm
mkdir ~/.nvm
nano ~/.bash_profile
```
U `.bash_profile` ili `~/.zshrc` ili odgovarajuci fajl dodati:
```sh
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh
```
Posle toga moze da se koristi `nvm install xxxxxxxx` ili `nvm ls-remote`

## Ostalo
### Visual Studio Code:
Install pomocu `brew cask install visual-studio-code` a podesavanja su objasnjena u [https://github.com/dmilojkovic76/coding-setups/blob/master/vscode-settings.md](vscode-settings.md) fajlu ovog repositorija.
Ostaje i `npm install -g eslint`

### Android Studio
Download i install [https://developer.android.com/studio](Android studio) a onda ga pokrenuti i instalirati __Android SDK, Android SDK Platform-Tools i Android SDK Build-Tools__

### Xcode
Install >Xcode 9.0 sa [https://developer.apple.com/xcode/](web download) ili [https://itunes.apple.com/us/app/xcode/id497799835](Mac App Store).
Configure the Xcode command-line tools to use the newly-installed version of Xcode by running the following from the command line:
```sh
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
```

### Flutter
Proveri prvo da li sistem ima `bash, mkdir, rm, git, curl, unzip, which` pa onda sa [https://flutter.io](flutter.io) skinuti Flutter SDK i instalirati pomocu:
```sh
cd ~
unzip ~/Downloads/flutter_macos_v1.0.0-stable.zip
mv ~/flutter ~/.flutter
```
Sledece treba dodati `export PATH=$PATH:~/.flutter/bin` u .zshrc ili .bashrc ili .bashrc_profile ili odgovarajuci fajl. Posle ponovnog pokretanja terminala sa `flutter doctor` proveriti konfiguraciju.

Na [https://flutter.io/docs/get-started/install/macos](flutter.io getting started) strani je objasnjeno podesavanje za iOS i Android.

Takodje treba dodati pluginove u Android Atudio u Visual Studio Code.

## Moj ceo `~/.zshrc`
```sh
# Setup nvm - Node Version Controll
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh

# Make ls command display coloured file names
alias ls='ls -G'
alias lal='ls -al'

# Load Nerd Fonts with Powerlevel9k theme for Zsh
POWERLEVEL9K_MODE='nerdfont-complete'
source ~/.powerlevel9k/powerlevel9k.zsh-theme

# JavaScript Prompt
POWERLEVEL9K_CUSTOM_JAVASCRIPT="echo -n '\ue781' JavaScript"
POWERLEVEL9K_CUSTOM_JAVASCRIPT_FOREGROUND="black"
POWERLEVEL9K_CUSTOM_JAVASCRIPT_BACKGROUND="yellow"

# Python prompt
POWERLEVEL9K_CUSTOM_PYTHON="echo -n '\uf81f' Python"
POWERLEVEL9K_CUSTOM_PYTHON_FOREGROUND="black"
POWERLEVEL9K_CUSTOM_PYTHON_BACKGROUND="blue"

# Customise the Powerlevel9k prompts
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(ssh dir vcs newline status)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=()
POWERLEVEL9K_PROMPT_ADD_NEWLINE=true

# Load Zsh tools for syntax highlighting and autosuggestions
HOMEBREW_FOLDER="/usr/local/share"
source "$HOMEBREW_FOLDER/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh"
source "$HOMEBREW_FOLDER/zsh-autosuggestions/zsh-autosuggestions.zsh"
```
