# setup  dotconfig for  MacOS
main idea to  store config file in git come from  [hacker-new](https://news.ycombinator.com/item?id=11071754)

add new  dot config git tracker
```
    git init --bare $HOME/.myconf
    alias dot_config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
    dot_config config status.showUntrackedFiles no
```

add dot config to login promp  (in my case: .zshrc)
```
    alias dot_config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'

```


add new file
```
    dot_config status
    dot_config add .vimrc
    dot_config commit -m "Add vimrc" 
```


for clone to new machine

```
   git clone --separate-git-dir=~/.myconf /path/to/repo ~
```

or if have  problem about already have git 
```
    git clone --separate-git-dir=$HOME/.myconf /path/to/repo $HOME/myconf-tmp
    cp ~/myconf-tmp/.gitmodules ~  # If you use Git submodules
    rm -r ~/myconf-tmp/
```

