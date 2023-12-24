# tmux-sessionizer

An iteration on [ThePrimeagen/tmux-sessionizer](https://github.com/ThePrimeagen/.dotfiles/blob/master/bin/.local/scripts/tmux-sessionizer).

TODO: get to session from detached state

|tmux       |Terminal|Selection               |Result                      |
|-----------|--------|------------------------|----------------------------|
|not running|N/A     |new name                |create and attach to session|
|running    |detached|preexisting session name|print "no current client"   |
|running    |detached|new name                |print "no current client"   |
|running    |attached|this session name       |no change                   |
|running    |attached|preexisting session name|switch to session           |
|running    |attached|new name                |create and switch to session| 
