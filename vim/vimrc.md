
Window Path : ${HOME}
Linus/MacOS Path : ~


```
source $VIMRUNTIME/vimrc_example.vim
"source $VIMRUNTIME/mswin.vim
"behave mswin

" Windows OS
"au GUIEnter * simalt ~x
" Linux OS, need to install wmctrl 
"au GUIEnter * call MaximizeWindow()
"function! MaximizeWindow()
"silent !wmctrl -r :ACTIVE: -b add,maximized_vert,maximized_horz
"endfunction

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
    "set guifont=Fantasque_Sans_Mono:h14 "Windows
    "set guifont=Fantasque\ Sans\ Mono\ 14 "Linux/MacOSX
    set guifont=Monaco\ 12
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
"if has("gui_running")
    set guioptions-=m
    "set guioptions-=T
    "set guioptions-=L 
    "set guioptions-=r  
    "set guioptions-=b
"endif

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

" vim-plug 
call plug#begin('~/.vim/plugged') " Linux
"call plug#begin('C:\Users\baitong\vimfiles\plug') " Windows
Plug 'Shougo/neocomplete.vim'
Plug 'vim-airline/vim-airline'
call plug#end()
"" Shorthand notation; fetches https://github.com/junegunn/vim-easy-align
"Plug 'junegunn/vim-easy-align'
"" Any valid git URL is allowed
"Plug 'https://github.com/junegunn/vim-github-dashboard.git'
"" Multiple Plug commands can be written in a single line using | separators
"Plug 'SirVer/ultisnips' | Plug 'honza/vim-snippets'
"" On-demand loading
"Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
"Plug 'tpope/vim-fireplace', { 'for': 'clojure' }
"" Using a non-master branch
"Plug 'rdnetto/YCM-Generator', { 'branch': 'stable' }
"" Using a tagged release; wildcard allowed (requires git 1.9.2 or above)
"Plug 'fatih/vim-go', { 'tag': '*' }
"" Plugin options
"Plug 'nsf/gocode', { 'tag': 'v.20150303', 'rtp': 'vim' }
"" Plugin outside ~/.vim/plugged with post-update hook
"Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
"" Unmanaged plugin (manually installed and updated)
"Plug '~/my-prototype-plugin'

" new-omni-completion
filetype plugin indent on
set completeopt=longest,menu

" NeoComplete
let g:acp_enableAtStartup=0
let g:neocomplete#enable_at_startup=1
let g:neocomplete#enable_smart_case=1
let g:neocomplete#sources#syntax#min_keyword_length=3
let g:neocomplete#lock_buffer_name_pattern='\*ku\*'
let g:neocomplete#sources#dictionary#dictionaries={
    \ 'default' : '',
    \ 'vimshell' : $HOME.'/.vimshell_hist',
    \ 'scheme' : $HOME.'/.gosh_completions'
    \ }
if !exists('g:neocomplete#keyword_patterns')
    let g:neocomplete#keyword_patterns = {}
endif "define keyword.
let g:neocomplete#keyword_patterns['default']='\h\w*'
inoremap <expr><TAB>  pumvisible() ? "\<C-n>" : "\<TAB>" 
"inoremap <expr><Space> pumvisible() ? neocomplete#close_popup() : "\<Space>"
let g:neocomplete#enable_auto_select=1
if !exists('g:neocomplete#sources#omni#input_patterns')
  let g:neocomplete#sources#omni#input_patterns={}
endif

" EasyGre
"let g:EasyGrepMode=2
"let g:EasyGrepCommand=0
"let g:EasyGrepRecursive=0
"let g:EasyGrepIgnoreCase =1
"let g:EasyGrepFilesToExclude="*.bak, *~, cscope.*, *.a, *.o, *.pyc, *.bak"

```

