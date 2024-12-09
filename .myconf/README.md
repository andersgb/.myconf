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

## Checking out on a new machine

A new checkout will fail when home directory is not empty, follow these steps instead:

```
    git clone --separate-git-dir=$HOME/.myconf /path/to/repo $HOME/myconf-tmp
    rm -r ~/myconf-tmp/
    alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
```

Now `config status` or `config reset HEAD --hard` etc will work in home dir, but take care about preserving any existing files there first.
