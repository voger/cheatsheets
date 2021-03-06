This is my cheat sheet for spacemacs with evil mode. It will be updated every time
I discover something interesting for my workflow. It contains both spacemacs and evil edit
commands.


A better cheatsheet for dired can be found in the [ GNU website ]( https://www.gnu.org/software/emacs/refcards/pdf/dired-ref.pdf )


## Getting Help

Command         | Description
----------------|---------------------------------------------------------
 **SPC h d f**  |Help for specific functions.


## Buffers/Windows
Command            | Description
-------------------|---------------------------------------------------------
**Spc f f**        | Find/create file. Also creates necessary parent folders
**C-\`**           | Find file (custom)
**Spc p f**        | Find/create file in the current project. Also creates necessary parent folders
**Spc f s**        | Save file
**:w Ret**         | Save file
**Spc b b**        | Find open buffer
**C-&lt;tab&gt;**  | Find open buffer (custom)
**C-x 4 f**        | Find file and open it in other window
**C-x 4 b**        | Open buffer in other window
**Spc w d**        | Close current window
**Spc f E**        | Edit current buffer as sudo (elevated privileges)


## Editing text
Command                                      |Description
---------------------------------------------|---------------------------
**ysiw**                                     | (evil) Surround word with text (parenthesis, tags etc.)
**ys$**                                      | (evil) Surround to the end of line with text (parenthesis, tags etc.)
**v{motion}s)**                              | (evil) Select with visual and surround with parenthesis. Also works with braces, tags etc.
**cs]}**                                     | (evil) Change surround from **]** to **}**
**v{motion}sf**                              | (evil) surround with function.
**"_dd**                                     | (evil) Delete line without affecting yank
**:%s/&lt;old text&gt;/&lt;new text&gt;**    | Replace old text with new text
**:%s/&lt;old text&gt;/&lt;new text&gt;/g**  | Replace old text with new text globaly in the buffer
**:%s/&lt;old text&gt;/&lt;new text&gt;/gc** | Replace old text with new text globaly in the buffer, confirm each replacement
**C-c h**                                    | Select all buffer
**g g V G**                                  | (evil) Select all buffer
**g g = G**                                  | (evil) Indent all buffer
**Spc j =**                                  | Indent all buffer


## Useful commands
Command                              |Description
-------------------------------------|---------------------------
**Spc a s t**                        | Popup ansi terminal in other window
**Spc p t**                          | Neotree find project root
**Spc f t**                          | Neotree toggle
**Spc f T**                          | Neotree show file
**, c P**                            | Preview markdown (vmd-mode)
**Spc f g**                          | rgrep. Search in directory
**Spc Spc comint-clear-buffer**      | Clear contents of current buffer
**Spc Spc buffer-menu-other-window** | Show a list of buffers in another window so we can manipulate them

## Alchemist
Command      |Description
---------------|---------------------------
**C-c a m l**  |Rerun the last mix task which was run by alchemist.
**C-c a n S**  |Run phoenix server

## Dired
Command      |Description
-------------|---------------------------
**Spc a d**  | Open dired
**Spc p D**  | Open dired in project
**Spc f j**  | Jump to file
**d**        | Mark file for deletion
**x**        | Execute deletion
**C-x C-q**  | While in dired toggle wdired mode to edit the file name live
**C-c C-c**  | While in wdired mode to exit in normal dired mode


## Magit
Command      |Description
-------------|---------------------------
**Spc g s**  | Open status buffer
**C-c C-c**  | Commit after comit message
