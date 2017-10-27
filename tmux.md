Commands that start with `$` are meant to be run in the shell
Commands that start with `:` are meant to be run in tmux after the `<Prefix> :`

## General
Command              | Description
---------------------|------------
*:rename-session**   | rename the session


Key                   | Description
----------------------|------------
q                     | Escape from various windows
<Prefix> :            | Run command
<Prefix> ?            | List key bindings
(copy-mode) /         | Search down
(copy-mode) S-/       | Search up

## Panes

Key                               | Description
----------------------------------|------------
<Prefix> %                        | Split verticaly
<Prefix> "                        | Split horizontaly
<Prefix> x                        | Kill pane
<Prefix> o                        | Cycle through panes
<Prefix> up, down, left, right    | Move through panes
<Prefix>-(up, down, left, right)  | Resize pane
<Prefix> q 1..9                   | Go to pane with number
<Prefix> z                        | Zoom in/out pane
<Prefix> Space                    | Cycle trough pane layouts




## Windows

Key           | Description
--------------|------------
<Prefix> c    | New window
<Prefix> ,    | Rename window
<Prefix> &    | Kill window
<Prefix> l    | Go to last window
<Prefix> 1..9 | Go to window number
<Prefix> p    | Go to previous window
<Prefix> n    | Go to next window
<Prefix> w    | Choose from a windows tree
<Prefix> f    | Find window by name



## Sessions

Key           | Description
--------------|------------
<Prefix> d    | Detach
<Prefix> s    | Switch to another session
<Prefix> (    | Switch to previous session
<Prefix> )    | Switch to next session


Command                       | Description
------------------------------|------------
$ tmux list-commands          | List available commands
$ tmux new-session -s <name>  | Create a new sessions with name <name>
$ tmux list-sessions          | List running sessions
$ tmux attach -t <name>       | Attach to the session <name>. If only one session is running the `-t` option can be omited.


