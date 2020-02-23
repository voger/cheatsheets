
1. [registers](#registers)
2. [global](#global)
3. [ex commands](#ex-commands)
4. [visual](#visual)
5. [buffer and file commands](#buffer-and-file-commands)
6. [windows](#windows)
7. [tabs](#tabs)
8. [motions](#motions)
9. [surround](#surround)
10. [markdown](#markdown)
11. [searching](#searching)
12. [fzf](#fzf)
13. [notes](#notes)

## Registers

| Register    | Description                                                                          |
|-------------|--------------------------------------------------------------------------------------|
| **".**      | Last inserted text                                                                   |
| **"#**      | Current file name                                                                    |
| **"/**      | Last search                                                                          |
| **"***      | OS Clipboard                                                                         |
| **"+**      | OS Clipboard (X11 middle click clipboard)                                            |
| **""**      | Last content of d, c, s, x, y commands                                               |
| **"-**      | Last content of d, c, s, x, y commands without new line                              |
| **"_**      | Black hole                                                                           |
| **"(a..z)** | Named registers a to z                                                               |
| **"0**      | The most recent yank                                                                 |
| **"(1..9)** | History register**s**. Not for yanks. They keep track of the most recent d, c, s, x. |


## Global

| Command              | Description                       |
|----------------------|-----------------------------------|
| **F2**               | Toggle hybrid/nonrelative numbers |
| **F7**               | Reformat buffer                   |
| **m{a-zA-Z}**        | Mark current cursor location      |
| **`{a-zA-Z}**        | Go to mark location               |
| **:browse oldfiles** | Browse recent files list          |

## Ex commands

| Command                                                     | Description                                                                     |
|-------------------------------------------------------------|---------------------------------------------------------------------------------|
| **:6t.**                                                    | Copy line 6 to just below the current line                                      |
| **:t6**                                                     | Copy the current line to just below line 6                                      |
| **:t.**                                                     | Duplicate the current line (similar to Normal mode yyp )                        |
| **:t$**                                                     | Copy the current line to the end of the file                                    |
| **:'<,'>t0**                                                | Copy the visually selected lines to the start of the file                       |
| **:[range]delete [x]**                                      | Delete specified lines [into register x]                                        |
| **:[range]yank [x]**                                        | Yank specified lines [into register x]                                          |
| **:[line]put [x]**                                          | Put the text from register x after the specified line                           |
| **:[range]copy {address}**                                  | Copy the specified lines to below the line specified by {address}               |
| **:[range]move {address}**                                  | Move the specified lines to below the line specified by {address}               |
| **:[range]join**                                            | Join the specified lines                                                        |
| **:[range]normal {commands}**                               | Execute Normal mode {commands} on each speci- fied line                         |
| **:[range]substitute/{pattern}/{string}/[flags]**           | Replace occurrences of {pattern} with {string} on each specified line           |
| **:[range]global/{pattern}/[cmd]**                          | Execute the Ex command [cmd] on all specified lines where the {pattern} matches |
| **:redir @+ &#124; messages &#124; redir END**              | Copy Ex command output to clipboard. See **:h redir** for files                 |
| **:redir @aCR**<br /> **:set allCR**<br /> **:redir ENDCR** | Alternate **redir** usage                                                       |
| **%s/\r//g**                                                | Remove carriage-return (^M) characters when copy pasting from PDF files         |

## Visual

| Command    | Description                                |
|------------|--------------------------------------------|
| **v**      | Enable character-wise Visual mode          |
| **V**      | Enable line-wise Visual mode               |
| **Ctrl-v** | Enable block-wise Visual mode              |
| **gv**     | Reselect the last visual selection         |
| **o**      | Go to other end of highlighted text        |
| **S}**     | Surround selection with } or whatever else |


## Buffer and file commands

| Command                        | Description                                                     |
|--------------------------------|-----------------------------------------------------------------|
| **\bv**, **\bs**               | Bufexplorer vertical/horizontal split                           |
| **\bd**, **\bu**, **\bu**      | Delete, unload, wipe buffer without closing the window          |
| **Ctrl-n**                     | Toggle NerdTree                                                 |
| **Ctrl-p**                     | Toggle Ctrl-p                                                   |
| **:e %%**                      | Expands files reliative path                                    |
| **:!mkdir -p %:h**             | Create directory structure of the current file when nonexistent |
| **:w !sudo tee % > /dev/null** | Write file with super user permissions                          |
| **:SudoWrite**                 | Write file with super user permissions                          |
| **:w &#124; %bd &#124; e#**    | Close all buffers except current                                |

## Windows

| Command                         | Description                                                                          |
|---------------------------------|--------------------------------------------------------------------------------------|
| **Ctrl-w s**                    | Split window horizontally                                                            |
| **Ctrl-w v**                    | Split window vertically                                                              |
| **Ctrl-w \|**                   | Maximize current vertical window                                                     |
| **Ctrl-w _**                    | Maximize current horizontal window                                                   |
| **Ctrl-w =**                    | Restore from maximize window                                                         |
| **:only**                       | Close other windows                                                                  |
| **Ctrl-w w**                    | Cycle open windows                                                                   |
| **Ctrl-w h, j, k, l**           | Move between windows                                                                 |
| **Ctrl-w H, J, K, L, R, r, x**  | Move windows around                                                                  |
| **Ctrl-w c**                    | Close current window                                                                 |
| **Ctrl-w o**                    | Close other windows                                                                  |
| **:sp[lit] {file}**             | Split horizontally, loading file                                                     |
| **:vsp[lit] {file}**            | Split vertically, loading file                                                       |
| **[N]Ctrl-w _**                 | **Resize** Set active window height to [N] rows                                      |
| **[N]Ctrl-w &#124;**            | **Resize** Set active window width to [N] columns                                    |
| **Ctrl-w [N] +** or **-**       | **Resize** Increase or decrease active window height by one or optionaly **N** rows  |
| **Ctrl-w [N] &lt;** or **&gt;** | **Resize** Increase or decrease active window width by one or optinaly **N** columns |
| **Ctrl-w =**                    | **Resize** Set windows same size                                                     |

## Tabs

| Command                       | Description                                                   |
|-------------------------------|---------------------------------------------------------------|
| **:tabe[dit] {filename}**     | New tab with filename                                         |
| **Ctrl-w T**                  | Move current window into new tab                              |
| **:tabc[lose]**               | Close the current tab page and all of its windows             |
| **:tabo[nly]**                | Keep the active tab page, closing all others                  |
| **:tabn[ext] {N}**, **{N}gt** | Switch to tab page number {N}. If {N} ommited proceed to next |
| **:tabn[ext]**, **gt**        | Switch to the next tab page                                   |
| **:tabp[revious]**, **gT**    | Switch to the previous tab page                               |
| **:tabmove [N]**              | Rearrange tabs                                                |


## Motions

| Motion | Description                                |
|--------|--------------------------------------------|
| **;**  | Repeat **f**, **F**, **t**, **T** forward  |
| **,**  | Repeat **f**, **F**, **t**, **T** backward |

## Surround

| Command         | Description                                        |
|-----------------|----------------------------------------------------|
| **ys{count}]**  | Surround {count} chars with ], }, ), t or whatever |
| **ys{object}f** | Surround {objext} with function                    |
| **S}**          | Surround selection with } or whatever else         |


## Markdown

|Command            | Description|
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------
|**:TableFormat**   | Format current into a table. Must have a second line as the second line of the table. That line must have as many pipes (**&#124;**) as table coulmns.|
|**Ctrl-m**         | Preview markdown|

## Searching

| Command                                      | Description                |
|----------------------------------------------|----------------------------|
| **:Ack [options] {pattern} [{directories}]** | Search                     |
| **\bs**                                      | BufExplorerHorizontalSplit |
| **\bv**                                      | BufExplorerVerticalSplit   |
| **\bt**                                      | ToggleBufExplorer          |

## fzf

| Command    | Description        |
|------------|--------------------|
| **Ctrl-t** | Open in new tab    |
| **Ctrl-x** | Open in new split  |
| **Ctrl-v** | Open in new vsplit |

## Notes

**Filename modifiers:**

| Command                    | Description                     |
|----------------------------|---------------------------------|
| `:help filename-modifiers` | to see the available modifiers. |
| `:echo expand('%:t')`      | to test the modifiers           |

