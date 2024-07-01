# my-mac
# myWindows
## 工具类-v5

### brew
[软件包安装工具](https://brew.sh/)

### nvim


`.config/nvim/init.vim`

```
set number
set relativenumber
set hidden
set encoding=UTF-8
set signcolumn=yes
" 高亮搜索
set hlsearch
" 复制到粘贴板
set clipboard+=unnamedplus

" map
nnoremap <silent> <Leader>f :Rg<CR>
nnoremap <C-t> :NERDTreeToggle<CR>
nnoremap <C-f> :Files<CR>
map <esc> :noh <CR>

" var
let g:coc_global_extensions = [
\ 'coc-json',
\ 'coc-tsserver',
\ 'coc-html',
\ 'coc-css',
\ 'coc-yaml',
\ '@yaegassy/coc-volar',
\ 'coc-prettier',
\ ]

" plugin
call plug#begin(has('nvim') ? stdpath('data') . '/plugged' : '~/.vim/plugged')

Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
Plug 'junegunn/fzf.vim'
Plug 'preservim/nerdtree'
Plug 'neoclide/coc.nvim', {'branch': 'release'}
Plug 'tpope/vim-fugitive'
Plug 'folke/tokyonight.nvim', { 'branch': 'main' }
" Bracket pair colorization
Plug 'lukas-reineke/indent-blankline.nvim'
" Managing tabs, buffers
" Plug 'nvim-tree/nvim-web-devicons' " Recommended (for coloured icons)
Plug 'ryanoasis/vim-devicons'
Plug 'akinsho/bufferline.nvim', { 'tag': 'v3.*' }
Plug 'windwp/nvim-autopairs'

call plug#end()

" markmap
command! -range=% Markmap CocCommand markmap.create <line1> <line2>

" coc-prettier
command! -nargs=0 Prettier :call CocAction('runCommand', 'prettier.formatFile')

" folke tokyonight
colorscheme tokyonight-storm

" 将 Grep 替换为 Rg
set grepprg=rg\ --vimgrep\ --smart-case\ --follow

" bufferline
set termguicolors
lua << EOF
require("bufferline").setup{}
require("nvim-autopairs").setup {}
EOF

```
icon 展示问题：
1. [安装字体](https://github.com/ryanoasis/nerd-fonts#option-4-homebrew-fonts)
iTerm2 → Preferences → Profiles → Text

2. 搜索
```shell
brew install fzf
brew install ripgrep
```

### 开发相关

- nvm
- nrm

### 命令行工具

- ripgrep
- fzf

### Alfred

插件：
1. [翻译](https://github.com/wensonsmith/YoudaoTranslator)

