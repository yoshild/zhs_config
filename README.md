# ZSH config

This project is just to show you my config and specify the color of the "fino-time" theme.

Here is the result of the configuration. If you want, you can change the color. I will explain how to do it.

![image example](https://github.com/yoshild/zhs_config/blob/main/Capture%20d%E2%80%99%C3%A9cran%20du%202023-12-04%2016-37-22.png)

First, make sure you have zsh installed on your device.
Navigate to your `.oh-my-zsh` directory:

```bash
cd ~/.oh-my-zsh/

```

Inside the `themes` directory, you will find all the themes for zsh. We will focus on the "fino-time" theme, so open the `fino-time.zsh-theme` file:

```bash
cd themes/
vim fino-time.zsh-theme

```

Copy the following code:

```

# fino-time.zsh-theme

# Use with a dark background and 256-color terminal!
# Meant for people with RVM and git. Tested only on OS X 10.7.

# You can set your computer name in the ~/.box-name file if you want.

# Borrowing shamelessly from these oh-my-zsh themes:
#   bira
#   robbyrussell
#
# Also borrowing from <http://stevelosh.com/blog/2010/02/my-extravagant-zsh-prompt/>

function virtualenv_info {
    [ $VIRTUAL_ENV ] && echo '('`basename $VIRTUAL_ENV`') '
}

function prompt_char {
    git branch >/dev/null 2>/dev/null && echo 'ツ➔ ' && return
    echo '○'
}

function box_name {
  local box="${SHORT_HOST:-$HOST}"
  [[ -f ~/.box-name ]] && box="$(< ~/.box-name)"
  echo "${box:gs/%/%%}"
}
#            your name machine                at                               your name                              in                             "where you are in your file"
PROMPT="╭─%{$FG[040]%}%n%{$reset_color%} %{$FG[239]%}at%{$reset_color%} %{$FG[086]%}$(box_name)%{$reset_color%} %{$FG[239]%}in%{$reset_color%} %{$terminfo[bold]$FG[082]%}%~%{$reset_color%}\\$(git_prompt_info)\\$(ruby_prompt_info) %{$FG[159]%}%D{%Y-%m-%d %H:%M:%S}%{$reset_color%}
╰─\\$(virtualenv_info)\\$(prompt_char) "
# on "branch of your git"
ZSH_THEME_GIT_PROMPT_PREFIX=" %{$FG[239]%}on%{$reset_color%} %{$FG[033]%}"
ZSH_THEME_GIT_PROMPT_SUFFIX="%{$reset_color%}"
ZSH_THEME_GIT_PROMPT_DIRTY="%{$FG[196]%}✘✘✘"
ZSH_THEME_GIT_PROMPT_CLEAN="%{$FG[046]%}✔"
ZSH_THEME_RUBY_PROMPT_PREFIX=" %{$FG[239]%}using%{$FG[243]%} ‹"
ZSH_THEME_RUBY_PROMPT_SUFFIX="›%{$reset_color%}"

```

If you want to change the color, replace the digit with the desired color.

```
%{$FG[040]%}%n%{$reset_color%}

```

Run the following command:

```bash
spectrum_ls

```

This command will display all the colors available in your terminal. Simply view the number assigned to each color and replace the corresponding number in the file.
Now restart your terminal and you will have your awesome custom terminal.
