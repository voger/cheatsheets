## Registers

Register                    | Description
----------------------------|----------------------------------------
**".**                      | Last inserted text
**"#**                      | Current file name
**"/**                      | Last search
**"***                      | OS Clipboard
**"+**                      | OS Clipboard (X11 middle click clipboard)
**""**                      | Last content of d, c, s, x, y commands
**"-**                      | Last content of d, c, s, x, y commands without new line
**"_**                      | Black hole
**"(a..z)**                 | Named registers a to z
**"0**                      | The most recent yank
**"(1..9)**                 | History register**s**. Not for yanks. They keep track of the most recent d, c, s, x.


## Global

Command         | Description
--------------- | ----------------------------------------
**F2**          | Toggle hybrid/nonrelative numbers
**m{a-zA-Z}**	| Mark current cursor location
**`{a-zA-Z}**	| Go to mark location


## Buffer and file commands

Command                                         | Description
----------------------------------------------- | ----------------
**\bv**, **\bs**                                | Bufexplorer vertical/horizontal split
**&lt;Tab&gt;**, **&lt;Shift&gt;-&lt;Tab&gt;**  | Cycle through buffers
**&lt;Ctrl&gt;-n**                              | Toggle NerdTree
**&lt;Ctrl&gt;-p**                              | Toggle Ctrl-p
**:e %%**                                       | Expands files reliative path
**:!mkdir -p %:h**                              | Create directory structure of the current file when nonexistent
**:w !sudo tee % > /dev/null**                  | Write file with super user permissions

## Windows

Command                               | Description
---------------                       | ----------------------------------------
**&lt;Ctrl-w&gt;s**                   | Split window horizontally
**&lt;Ctrl-w&gt;v**                   | Split window vertically
**&lt;Ctrl-w&gt;w**                   | Cycle open windows
**&lt;Ctrl-w&gt;h, j, k, l**          | Move between windows
**&lt;Ctrl-w&gt;H, J, K, L, R, r, x** | Move windows around
**&lt;Ctrl-w&gt;c**                   | Close current window
**&lt;Ctrl-w&gt;o**                   | Close other windows
**:sp[lit] {file}**                   | Split horizontally, loading file
**:vsp[lit] {file}**                  | Split vertically, loading file
**&lt;[N]Ctrl-w&gt;_**                | Set active window height to [N] rows
**&lt;[N]Ctrl-w&gt;|**                | Set active window width to [N] colimns


## Motions

Motion          | Description
--------------- | ----------------------------------------
**;**           | Repeat **f**, **F**, **t**, **T** forward
**,**           | Repeat **f**, **F**, **t**, **T** backward



## Markdown

Command            | Description
-----------------  | --------
**:Tabularize**    | Convert to table
**&lt;Ctrl&gt;-m** | Preview markdown
