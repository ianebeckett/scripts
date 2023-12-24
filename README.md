# tmux-sessionizer

An iteration on [ThePrimeagen/tmux-sessionizer](https://github.com/ThePrimeagen/.dotfiles/blob/master/bin/.local/scripts/tmux-sessionizer).

|tmux       |terminal|selection               |result                      |
|-----------|--------|------------------------|----------------------------|
|not running|        |new name                |create and attach to session|
|running    |detached|preexisting session name|print "no current client"   |
|running    |detached|new name                |print "no current client"   |
|running    |attached|this session name       |no change                   |
|running    |attached|preexisting session name|switch to session           |
|running    |attached|new name                |create and switch to session| 

Entering a session from a detached state is tricky for two reasons:
    -It's not obvious how to attach to a session, then continue running
        tmux commands from the script that made you attach.
    -We can't assume that a preexisting destination session is at the prompt.
        It could be in vim, for example.

Current workaround options:
    -If detached, first attach with `tmux a` <-- my preferred workaround
    -Avoid detached state by attaching to tmux in zshrc
    (I don't feel comfortable doing this)
    
I haven't accounted for multiple projects with the same base name. I intend to
avoid that situation for now.
