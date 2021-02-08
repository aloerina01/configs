#
# Executes commands at the start of an interactive session.
#
# Authors:
#   Sorin Ionescu <sorin.ionescu@gmail.com>
#

# Source Prezto.
if [[ -s "${ZDOTDIR:-$HOME}/.zprezto/init.zsh" ]]; then
  source "${ZDOTDIR:-$HOME}/.zprezto/init.zsh"
fi

# Customize to your needs...

export PATH=/usr/local:$PATH:/Users/JP21369/scripts:
export PATH="$HOME/.anyenv/bin:$PATH"

autoload -Uz compinit
compinit

setopt nonomatch

alias relogin='exec $SHELL -l'
alias n='npm'
alias ns='npm start'
alias nr='npm run'
alias nrs='npm run $(get_npm_scripts | peco)'
alias gl='git log --oneline'
alias wd='webdev'

# === cool-peco init ===
FPATH="$FPATH:/Users/JP21369/cool-peco"
autoload -Uz cool-peco
cool-peco
# ======================

bindkey "^r" cool-peco-history
bindkey "^e" search_npm_scripts

function get_npm_scripts () {
  cat package.json | jq -r '.scripts | keys[]'
}

function search_npm_scripts () {
  npm run $(get_npm_scripts | peco)
}

# widgetとして登録しbindkeyできる状態にする
zle -N search_npm_scripts

eval "$(anyenv init -)"
eval "$(nodenv init -)"

