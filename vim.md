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

Command              | Description
---------------------|-------------------------
**F2**               | Toggle hybrid/nonrelative numbers
**F7**               | Reformat buffer
**m{a-zA-Z}**        | Mark current cursor location
**`{a-zA-Z}**        | Go to mark location
**:browse oldfiles** | Browse recent files list

## Ex commands

Command                                           | Description
--------------------------------------------------|---------------------------------------------------------------------------------|
**:6t.**                                          | Copy line 6 to just below the current line
**:t6**                                           | Copy the current line to just below line 6
**:t.**                                           | Duplicate the current line (similar to Normal mode yyp )
**:t$**                                           | Copy the current line to the end of the file
**:'<,'>t0**                                      | Copy the visually selected lines to the start of the file
**:[range]delete [x]**                            | Delete specified lines [into register x]
**:[range]yank [x]**                              | Yank specified lines [into register x]
**:[line]put [x]**                                | Put the text from register x after the specified line
**:[range]copy {address}**                        | Copy the specified lines to below the line specified by {address}
**:[range]move {address}**                        | Move the specified lines to below the line specified by {address}
**:[range]join**                                  | Join the specified lines
**:[range]normal {commands}**                     | Execute Normal mode {commands} on each speci- fied line
**:[range]substitute/{pattern}/{string}/[flags]** | Replace occurrences of {pattern} with {string} on each specified line
**:[range]global/{pattern}/[cmd]**                | Execute the Ex command [cmd] on all specified lines where the {pattern} matches

## Visual

Command         | Description
--------        | --------
**v**           | Enable character-wise Visual mode
**V**           | Enable line-wise Visual mode
**&lt;C-v&gt;** | Enable block-wise Visual mode
**gv**          | Reselect the last visual selection
**o**           | Go to other end of highlighted text
**S}**          | Surround selection with } or whatever else


## Buffer and file commands

Command                                        | Description
-----------------------------------------------|-----------------------------------------------------------------|
**\bv**, **\bs**                               | Bufexplorer vertical/horizontal split
**\bd**, **\bu**, **\bu**                      | Delete, unload, wipe buffer without closing the window
**&lt;Tab&gt;**, **&lt;Shift&gt;-&lt;Tab&gt;** | Cycle through buffers
**&lt;Ctrl&gt;-n**                             | Toggle NerdTree
**&lt;Ctrl&gt;-p**                             | Toggle Ctrl-p
**:e %%**                                      | Expands files reliative path
**:!mkdir -p %:h**                             | Create directory structure of the current file when nonexistent
**:w !sudo tee % > /dev/null**                 | Write file with super user permissions

## Windows

Command                               | Description
--------------------------------------|--------------------------------------
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
**&lt;[N]Ctrl-w&gt;&#124;**           | Set active window width to [N] columns

## Tabs

Command                       | Description
---------------               | ----------------------------------------
**:tabe[dit] {filename}**     | New tab with filename
**&lt;Ctrl-w&gt;T**           | Move current window into new tab
**:tabc[lose]**               | Close the current tab page and all of its windows
**:tabo[nly]**                | Keep the active tab page, closing all others
**:tabn[ext] {N}**, **{N}gt** | Switch to tab page number {N}. If {N} ommited proceed to next
**:tabn[ext]**, **gt**        | Switch to the next tab page
**:tabp[revious]**, **gT**    | Switch to the previous tab page
**:tabmove [N]**              | Rearrange tabs


## Motions

Motion          | Description
--------------- | ----------------------------------------
**;**           | Repeat **f**, **F**, **t**, **T** forward
**,**           | Repeat **f**, **F**, **t**, **T** backward

## Surround
Command              | Description
-------------------- | --------------------
**ys{count}l]**      | Surround {count} chars with ], }, ), t or whatever
**ys{object}lf**     | Surround {objext} with function

## Markdown

Command            | Description
-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
**:TableFormat**   | Format current into a table. Must have a second line as the second line of the table. That line must have as many pipes (**&#124;**) as table coulmns.
**&lt;Ctrl&gt;-m** | Preview markdown

## Searching

Command                                       | Description
--------------------------------------------- | --------------------
**:Ack [options] {pattern} [{directories}]**  | Search
**\bs**                                       | BufExplorerHorizontalSplit
**\bv**                                       | BufExplorerVerticalSplit
**\bt**                                       | ToggleBufExplorer
