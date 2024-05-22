### Welcome to my dotfiles tracked with git

I am following the recipe from
https://news.ycombinator.com/item?id=11071754

I.e., this means it was set up like:
```
    git init --bare $HOME/.myconf
    alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
    config config status.showUntrackedFiles no
```

And we can track files like
```
    config status
    config add .vimrc
    config commit -m "Add vimrc"
    config add .config/redshift.conf
    config commit -m "Add redshift config"
    config push
```


