# fzf 
This is a [fzf](https://github.com/junegunn/fzf) fork which stores the search
position in the history, making it possible to resume the last session exactly
where it left off. I.e. if fzf in invoked via `fzf --history=<history_file>`,
pressing `ctrl-p` will not only restore the previous search pattern, but also
position the cursor to where it was at the previous candidate selection.
Multi-selection is restored too, but `-m` has to be specified. Without `-m`,
multi-selection will be ignored even if the history entry has it.

## Installation
Using `vim-plug`:
```
Plug 'mrbiggfoot/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
```
Or you can do these steps manually, or build from source.

## Caveats
- The candidate list **must** stay the same accross `fzf` invocations for the
  resume to work properly. Otherwise, the candidate will be chosen
  semi-randomly.
- The history files created by other versions of `fzf` need to be wiped out.
