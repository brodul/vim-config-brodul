::

bootstrap VAM
=============

::

    mkdir ~/.vim/addons -p
    mkdir ~/.vim/tmp -p
    mkdir ~/.vim/tmp/backup -p
    mkdir ~/.vim/tmp/swap -p
    mkdir ~/.vim/tmp/undo -p
    cd ~/.vim/addons
    git clone git://github.com/MarcWeber/vim-addon-manager.git


.vimrc
======

::

    set runtimepath+=~/.vim/addons/vim-addon-manager
    call vam#ActivateAddons(
        \ ['github:brodul/vim-config-brodul'],
        \ {'plugin_root_dir': $HOME.'/.vim/addons'})

    let mapleader=","
    let maplocalleader = "\\"

    call brodul#config()


    let g:tagbar_ctags_bin = '/var/run/current-system/sw/bin/ctags'

    let g:github_user = 'brodul'
    let g:github_token = 'XXXXXX'

    "set guifont=Terminus\ 9
    "set guifont=Consolas\ 10
    "set guifont=DejaVu\ Sans\ Mono\ 9
    "set guifont=Bitstream\ Vera\ Sans\ Mono\ 9
    set guifont=Bitstream\ Vera\ Sans\ Mono\ for\ Powerline\ 9
    set guioptions-=m

    let g:ctrlp_user_command = {
        \ 'types': {
            \ 1: ['.git/', 'cd %s && git ls-files'],
            \ 2: ['.hg/', 'hg --cwd %s locate -I .'],
            \ },
        \ 'fallback': 'find %s -type f'
        \ }

    let g:syntastic_javascript_checker = 'jshint'
