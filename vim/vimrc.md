
Window Path : ${HOME}

Linus/MacOS Path : ~


```

source $VIMRUNTIME/vimrc_example.vim
"source $VIMRUNTIME/mswin.vim
"behave mswin

" Linux, need to install wmctrl
"au GUIEnter * call MaximizeWindow()
"function! MaximizeWindow()
"silent !wmctrl -r :ACTIVE: -b add,maximized_vert,maximized_horz
"endfunction
" Windows
"au GUIEnter * simalt ~x
" macOS

"-------------------------------------------------------------------------------
" VIM Setting
"-------------------------------------------------------------------------------

" Close VI Compatible Mode
set nocompatible

" File Encodings
set fileencodings=utf-8,ucs-bom,gb18030,gbk,gb2312,cp936

" <leader>
"let mapleader=","
"let g:mapleader=","

" Syntax Highlight
syntax enable
syntax on
set showmatch

" Color Scheme
if has("gui_running")
    "colorscheme zellner "white backgroud
    "colorscheme elflord "black backgroud
    "colorscheme peachpuff
endif

" GUI Font
if has("gui_running")
    "set guifont=Fantasque\ Sans\ Mono\ 14 "Linux
    "set guifont=Fantasque_Sans_Mono:h14 "Windows/macOS
    "set guifont=Monaco\ 12
    "set guifont=Monaco:h12
endif

" Number of Command History
set history=200

" File Type
set ffs=unix,dos,mac

" No Backup
set nobackup
set nowb

" No Prsistent Undo
set noundofile

" Line Number
set nu!

" No Auto Wrap
set nowrap

" Tab
set expandtab
set tabstop=4
set softtabstop=4

" Disabled display Menu Bar, Tool Bar and Scroll Bars
if has("gui_running")
    set guioptions-=m
    "set guioptions-=T
    "set guioptions-=L
    "set guioptions-=r
    "set guioptions-=b
endif

" highlight current line/column
set cursorline
"set cursorcolumn

" Status Line
set statusline=[%F]%y%r%m%*%=[Line:%l/%L,Column:%c][%p%%]
set laststatus=2 "always show the status line
set ruler

" Search
set incsearch "incremental
set hlsearch  "highlight

" Indent
"set smartindent
"set autoindent
"set ai!

" Swith Window Once, not Twice
"nnoremap <C-J> <C-W><C-J> "Ctrl-j to move down a split
"nnoremap <C-K> <C-W><C-K> "Ctrl-k to move up a split
"nnoremap <C-L> <C-W><C-L> "Ctrl-l to move right a split
"nnoremap <C-H> <C-W><C-H> "Ctrl-h to move left a split

" Clear Spaces at the end of the line
"nmap <F7> :%s/\s\+$//g<cr>:noh<cr>

"-------------------------------------------------------------------------------
" Plugins Setting
"-------------------------------------------------------------------------------

" Load Tags When Start
if exists("tags")
    set tags=./tags
endif

" new-omni-completion
filetype plugin indent on
set completeopt=longest,menu

" vim-plug
call plug#begin('~/.vim/plugged') " Linux/macOS
"call plug#begin('C:\Users\xxx\vimfiles\plugged') " Windows
Plug 'vim-airline/vim-airline'
Plug 'skywind3000/vim-auto-popmenu'
Plug 'vhda/verilog_systemverilog.vim'
call plug#end()

" vim-auto-popmenu
" enable this plugin for filetypes, '*' for all files.
let g:apc_enable_ft = {'*':1}
" source for dictionary, current or other loaded buffers, see ':help cpt'
set cpt=.,k,w,b
" don't select the first item.
set completeopt=menu,menuone,noselect
" suppress annoy messages.
set shortmess+=c

" EasyGrep
"let g:EasyGrepMode=2
"let g:EasyGrepCommand=0
"let g:EasyGrepRecursive=0
"let g:EasyGrepIgnoreCase =1
"let g:EasyGrepFilesToExclude="*.bak, *~, cscope.*, *.a, *.o, *.pyc, *.bak"

```

