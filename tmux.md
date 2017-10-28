**`<Prefix> :list-keys`** or **`<Prefix> ?`** shows a list with key bindings
**`:list-commands`** lists available commands



## General
Command                       | Description
------------------------------|------------
**:rename-session**           | rename the session
**:capture-pane**             | Capture contents of the current pane in a buffer
**:clear-history -t 1**       | Clear history of pane 1
**$tmux-attach -t work**      | Attach session work


Key                                 | Description
------------------------------------|------------
**q**                               | Escape from various windows
**&lt;Prefix&gt; :**                | Enter command mode
**&lt;Prefix&gt; [**                | Enter copy mode
**&lt;Prefix&gt; ?**                | List key bindings
**(copy-mode) Esc**                 | Exit copy mode
**(copy-mode) /**                   | Search down
**(copy-mode) Shift-/**             | Search up
**(copy-mode) Space**               | Begin selection
**(copy-mode) y**                   | Yank selection
**(copy-mode) &lt;Prefix&gt; ]**    | Paste buffer
**&lt;Prefix&gt; =**                | Show buffer stack


## Panes

Key                                         | Description
--------------------------------------------|------------
**&lt;Prefix&gt; %**                        | Split verticaly
**&lt;Prefix&gt; "**                        | Split horizontaly
**&lt;Prefix&gt; x**                        | Kill pane
**&lt;Prefix&gt; o**                        | Cycle through panes
**&lt;Prefix&gt; up, down, left, right**    | Move through panes
**&lt;Prefix&gt;-(up, down, left, right)**  | Resize pane
**&lt;Prefix&gt;-(H, J, L, K)**             | Resize pane. Custom to my setup
**&lt;Prefix&gt; q **                       | Identify panes
**&lt;Prefix&gt; q 1..9**                   | Go to pane with number
**&lt;Prefix&gt; z**                        | Zoom in/out pane
**&lt;Prefix&gt; {**                        | Cycle **left position** of the pane in the layout
**&lt;Prefix&gt; }**                        | Cycle **right position** of the pane in the layout
**&lt;Prefix&gt; Space**                    | Cycle trough pane layouts
**&lt;Prefix&gt; !**                        | Break the pane (make it it's own window)




## Windows

Key           | Description
--------------|------------
**&lt;Prefix&gt; c**    | New window
**&lt;Prefix&gt; ,**    | Rename window
**&lt;Prefix&gt; &**    | Kill window
**&lt;Prefix&gt; l**    | Go to last window
**&lt;Prefix&gt; 1..9** | Go to window number
**&lt;Prefix&gt; p**    | Go to previous window
**&lt;Prefix&gt; n**    | Go to next window
**&lt;Prefix&gt; w**    | Choose from a windows tree
**&lt;Prefix&gt; f**    | Find window by name



## Sessions

Key                           | Description
------------------------------|------------
**&lt;Prefix&gt; d**          | Detach
**&lt;Prefix&gt; s**          | Switch to another session
**&lt;Prefix&gt; (**          | Switch to previous session
**&lt;Prefix&gt; )**          | Switch to next session
**:new-session -s "Another"** | Create and name a new session
**:kill-session -t "Another"**| Kill session

Command                                 | Description
----------------------------------------|------------
**$ tmux list-commands**                | List available commands
**$ tmux new-session -s &lt;name&gt;**  | Create a new sessions with name &lt;name&gt;
**$ tmux list-sessions**                | List running sessions
**$ tmux attach -t &lt;name&gt;**       | Attach to the session &lt;name&gt;. If only one session is running the `-t` option can be omited.


