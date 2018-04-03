#### My dev setting note

`.bash_profile`
```
# Show directory and git branch in iTerm tabs
if [ $ITERM_SESSION_ID ]; then
  export PROMPT_COMMAND='echo -ne "\033];${PWD##*/}\007"; ':"$PROMPT_COMMAND";
fi

# Git branch in prompt.
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1=" \e[95m\]>\[\033[00m\] \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```