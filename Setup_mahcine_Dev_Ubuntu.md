# Setup mahcine Dev Ubuntu:

## Installation des outils
* Install terminator `sudo apt-get install terminator`
* Install sublime text
* Install node and npm via [nvm](https://github.com/creationix/nvm)
    - No sudo required for packages installation. Yeah, it rocks!
    - eslint for js/jsx `npm install -g eslint`
    - sass-lint for scss `npm install -g sass-lint`

## Configuration de sublime text

* Install package control from here: [Package control](https://packagecontrol.io/)
* Add following packages to the "installed_packages" list (CTRL + Shift + p, then type `package control settings`):

```json
[
    "CodeFormatter",
    "Color Highlighter",
    "Dockerfile Syntax Highlighting",
    "Emmet",
    "ES6-Toolkit",
    "EsFormatter",
    "Expand Selection to Quotes",
    "Expand Selection to Whitespace",
    "FileDiffs",
    "FuzzyFileNav",
    "FuzzyFilePath",
    "Git",
    "Git Config",
    "GitGutter",
    "HTMLBeautify",
    "JavaScript Completions",
    "JavaScriptNext - ES6 Syntax",
    "JSON Reindent",
    "JSX",
    "LineEndings",
    "MarkdownEditing",
    "nginx",
    "Pretty JSON",
    "React ES6 Snippets",
    "React Templates",
    "ReactJS",
    "ReactJS Snippets",
    "SCSS",
    "SideBarEnhancements",
    "SingleTrailingNewLine",
    "SublimeLinter",
    "SublimeLinter-contrib-eslint",
    "SublimeLinter-contrib-sass-lint",
    "SublimeLinter-contrib-scss-lint"
]
```

* Add configuration for sublime text (CTRL + Shift + p, `preferences: settings`) [this content](./sublime_text_settings/Preferences.sublime-settings)

* Setup CodeFormatter (preferences > CodeFormatter > Settings user) with [this content](./sublime_text_settings/CodeFormatter.sublime-settings)

* Use git to have a backup of your config, and commit it regulary!
    - OSX: ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/
    - Ubuntu: ~/.config/sublime-text-2/Packages/User/

## Install Meteor

Run this command in your shell to install meteor `curl https://install.meteor.com/ | sh`

## Configure git

* Put this file `./gitconfig` into your home folder `cp gitconfig ~/.gitconfig`

## Configure your shell (zsh + prezto)

```bash
sudo apt-get install zsh
zsh
git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done
chsh -s /bin/zsh
```
