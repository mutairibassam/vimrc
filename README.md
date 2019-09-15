# vimrcFile
 
### vimrc file is hidden file that will upgread your vim terminal by adding colors, status mode, line numbers and without any plugins.
 
1- Open your terminal

2- Open your vimrc file:

`open .vimrc`


3- Paste only what you want to be added:

```
:set laststatus=2   " statuslne
:set number         " set numbers
syntax on
set relativenumber
set ruler
set expandtab
set smarttab
set shiftwidth=2
set tabstop=2


" Disable arrows to improve your (hjkl) movements
map <Down> <NOP>
map <Up> <NOP>
map <Left> <NOP>
map <Right> <NOP>


function! InsertStatuslineColor(mode)
if a:mode == 'i'
hi statusline guibg=Cyan ctermfg=6 guifg=Black ctermbg=0
elseif a:mode == 'r'
hi statusline guibg=Purple ctermfg=5 guifg=Black ctermbg=0
else
hi statusline guibg=DarkRed ctermfg=1 guifg=Black ctermbg=0
endif
endfunction


au InsertEnter * call InsertStatuslineColor(v:insertmode)
au InsertLeave * hi statusline guibg=DarkGrey ctermfg=8 guifg=White ctermbg=15
" default the statusline to green when entering Vim
hi statusline guibg=DarkGrey ctermfg=8 guifg=White ctermbg=15


" Formats the statusline
set statusline=%f                           " file name
set statusline+=\ %y      "filetype
set statusline+=%h      "help file flag
set statusline+=%m      "modified flag
set statusline+=%r      "read only flag
set statusline+=\ %=                        " align left
set statusline+=Line:%l/%L
set statusline+=\ Buf:%n                    " Buffer number
set statusline+=\ [%b][0x%B]\               " ASCII and byte code under cursor
set statusline+=[%{&ff}] "file format
```


4- Press _ESC_ and Type _:wq_

5- Reopen your terminal.
