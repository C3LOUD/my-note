---
url: https://frontendmasters.com/courses/vim-fundamentals/
format: video
type: learning
status: in-progress
current: ch3-9
---

### Fundamental
- `zz` - Recenter the cursor
- Yank will only keep the register for only index 0, thus yank will be overwrite on index 0
- Delete will keep the register for index 0 and all the way down thus delete will keep the entire history
- `p` - How paste work is to paste the `"` register (Double quote register)
### Customization
- `set scrolloff=x` - x means how many lines away to auto scroll
- `set relativenumber` - enable line number in relative mode, `set rnu` for abbreviation
- `set tabstop=4 softtabstop=4`
- `set shiftwidth=4`
- `set expandtab`
- `set smartindent`
- Read `:h` for manual
- `:h options`
- `:h <tabcomplete or ctrl-d>`
- `:h <specific option name>`
- `Tab` for autocompletion
- NetRW - default plugin for browsing the filesystem
- `<CR>` - stands for Carriage Return, when clicking enter, in CR mode, it will append `\r`at the end of the line
- `<LF>` - stands for Line Feed, when clicking enter, in LF mode, it will append `\n` at the end of the line
- `<CRLF>` - the combination mode of CR and LF which will append `\n\r` at the end of the line
- `:Ex` - replace current buffer with explorer view
- `:Vex` - open explorer on the side, vertically
- `:Sex` - open explorer horizontally, `S` stands for split
- `C-w` - to window mode, `v` to open window vertically, `s` to open window horizontally, combine with `ijkl` to navigate between different window
- `C-o`- close all window without current window
- `let mapleader = " "` - set the leader key
- `nnoremap <leader>pv :Vex<CR>` - `nnoremap` is a command combine several things
	- `n` - mode the command to bind, `n` for normal mode, `i` for insert mode, `v` for visual mode, `c` for command mode, `t` for terminal mode
	- `nore` - no recursive execution, which means the command you setup will NOT propagate further, the command will stay what it is I setup, if there is another map of the command I use in the map, which is nested mapping, it will not work.
	- `map` - command itself, here using `map` command
	- `<leader>pv` - Primeagen choose pv which stands for project view, but you can choose anything you like
	- ` ` - remember to add a blank space to split the right hand side and the left hand side
	- `:Vex<CR>` - the real command want to trigger, put on the left hand side, also put what you need here
- `so %` - `so` stands for source, reload the file you want, `%` is the placeholder means the current file you are in
- Tips from Prime, 3 character is the optimal character length for remap
- `:e` - in directory, it means edit, which will open the file, you can do fuzzy finding for the file with this like `:e **any*thing` and click `tab` or `<C-d>` for suggestion
- `m <Letter>` - add bookmark
- `' <Letter>` - portal to bookmark
- Capital letter register global bookmark cross buffer, lower case only register in the current buffer
- The setting or key mapping should have reusability and some kinds of convention for your mental model, if not, it just overload your brain
- In register, `:reg` it kept the current file init with `%` sign, and there is a sign `#` that store previous file, using `<C-^>` can quickly navigate to the previous file
- `<C-O>` to hop the history of navigation backwards, `<C-I>` hop the history of navigation forwards
- `_` - move to the head of line at first none black character; `0` - move to the first character of the line; `$` - move to the end of the line
- `,` - forward, `;` - backward
- `f` - forward to; `t` - go to, stop in front of the target. Capitalize will reverse the direction
- 