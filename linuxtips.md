# Linux tips
## CLI trouble shooting
follow a log file
  `tail -f`
## SSH commands
Turn on SSH
  `service shh start`

Restart ssh
  `service ssh restart`

## File permission
view permissions for a file
  `ls -l`

when viewing file permissions there are three user based permissions groups, "owner, group, all users". the three permissions that can be given are "R" read, "W" write, "X" execute. `_RWXRWXRWX` this indicates that owner, group, and all users have the permissions to read, write, and execute.

assigning permissions
  `chmod` followed by designated group followed by + or - then the permission and file name eg. `chmod a+rw filename.sh` this would give read and write to all users for filename.sh

assigning permissions with binary
  `chmod 640 filename.sh` would give read and write to owner, read to groups, and no permissions to all users.

R = 4, W = 2, X = 1. RWX = 7, RW = 6

## System commands
check for system updates
  `sudo apt-get update`

check for programs that have available upgrades
  `sudo apt list --upgradeable`

install upgrades for specific programs
  `sudo apt-get upgrade <program name>`

## TMUX
tmux is an awesome tool that gives you a terminal session on a server so that if you lose your connection or ssh session you can continue where you left off.

Create new session (replace xxx with whatever you want, maybe mail):
`tmux new-session -s xxx`

Attach to an existing session (replace xxx with the session name):
`tmux a -d -t xxx`

To output a list of what sessions exist use:
`tmux ls`

tmux uses a prefix which is a key combo that tells tmux you want to perform a tmux command. The default is ctrl+b, I recommend keeping the default because when you work in multiple environments it's a pain to transfer custom settings.

When you are in tmux you have a status bar at the bottom and when you first start a session you have 1 window. You can create more windows and even panes (split windows). For debugging it can be really helpful to have a window with 2 panes split vertically.

On the left pane you run your commands and on the right pane you tail a log.

So after you have attached to a tmux session here are some steps to create a split pane window and moving around.

Split the window into two vertical panes
> ctrl+b %

You can change the pane you want to type in by
> ctrl+b <direction-keys>

or cycle through panes with
> ctrl+b o

If you'd like to keep your tmux session alive but you want to get out of tmux you detach
> ctrl+b d

If you want to kill your session you can enter 'exit' in all the panes or detach and enter
`tmux kill-session -t xxx`

If you see a tmux command that starts with a colon (:) you
> ctrl+b :
This will put the cursor in the tmux status bar and you can type the command.

Here is a handy cheatsheet: https://gist.github.com/MohamedAlaa/2961058
and this one: https://tmuxcheatsheet.com/



## TODO
* SSH
