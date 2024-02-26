# innit

git clone https://github.com/jaderiverstokes/vimjob ~/.vim
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
ln ~/.vim/vimrc ~/.vimrc

sudo add-apt-repository -y ppa:jonathonf/vim
sudo apt install -y vim
sudo apt install -y silversearcher-ag

# Append the custom configurations to .bashrc
{
    echo "# calm"
    echo "touch ~/.hushlogin"
    echo "export PS1='> '"
    echo "export BASH_SILENCE_DEPRECATION_WARNING=1"
    echo ""
    echo "# vi"
    echo "set -o vi"
    echo "export EDITOR=vim"
    echo "bind TAB:menu-complete"
    echo "bind '\"jk\":vi-movement-mode'"
    echo "bind '\"kj\":vi-movement-mode'"
    echo "bind '\"kk\":vi-movement-mode'"
    echo ""
    echo "shopt -s expand_aliases"
    echo "alias v='vim README.md'"
    echo "alias g=\"git\""
    echo "alias skrr=\"exit\""
    echo "alias com=\"git add .;git commit --no-verify -m\""
} >> ~/.bashrc


# Set the content of ~/.gitconfig
cat << EOF > ~/.gitconfig
[user]
	name = jaderiverstokes
	email = jaderiverstokes@gmail.com
[core]
    excludesfile = ~/.gitignore
[color]
    branch = auto
    diff = auto
    interactive = auto
    status = auto
    grep = auto
[alias]
    lol = log --graph --oneline --decorate --color --all
    co = checkout
    pb = pull
    p = pull
    br = branch
    st = status
    rect = commit --amend --no-edit
[push]
	default = current
[filter "lfs"]
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
	clean = git-lfs clean -- %f
EOF


ssh-keygen -q -N "" -f ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
