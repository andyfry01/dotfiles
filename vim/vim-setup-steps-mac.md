1 Steps followed for vim setup: 

1. Install neovim: `brew install neovim`
2. Install VimR: download from [vimr.org](http://vimr.org/)
3. Update python3 if needed: `brew install python`
4. Configure neovim:
	(from within VimR)
	1. `:call mkdir(stdpath('config'), 'p')`
	2. `:exe 'edit '.stdpath('config').'/init.vim'`
	3. Add following to file: 
		set runtimepath^=~/.vim runtimepath+=~/.vim/after
		let &packpath = &runtimepath
		source ~/.vimrc
5. Install python3: `brew install python3`
5a. If step five fails, fix brew by doing this: `sudo install -d -o $(whoami) -g admin /usr/local/Frameworks`
5b. `brew reinstall python3`
6. If VimR gives you errors about the ultisnips package needing Python >=2.3 or 3, reinstall Python neovim package: `pip3 install neovim`
7. Install vim-plug package manager (note: installation instructions are for neovim, not normal vim)i
	curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
8. Add vim-plug config to neovim rc file (/.config/nvim/init.vim): 
	call plug#begin('~/.local/share/nvim/plugged')
	" packages go here, sample syntax: 
	" Plug 'ayu-theme/ayu-vim'
	call plug#end()
9. Add desired packages (see above for sample syntax
10. Add color theme to neovim rc file: 
	call plug#begin('~/.local/share/nvim/plugged')
	Plug 'https://github.com/rakr/vim-one'
	call plug#end()

	colorscheme one
	set background=dark " for the dark version
	" set background=light " for the light version
11. Add emmett to vim: 
	Plug 'https://github.com/mattn/emmet-vim'
