Latex-Suite for Vim
===================

This is a mirror of the official vim-latex repository
for use in Vim Janus (https://github.com/carlhuda/janus).
It has some Mac-specific modifications to make it work
more sensible out of the box on Mac OS X,
such as using Skim for PDF sync etc.


Prerequisites
-------------
See the latex-suite docs for details. You should at least have 
(Mac)Vim, Janus and a latex distribution installed.


Installing
----------

Installing vim-latex with Janus is easy. Just add the following line
to your local rake definitions in _~/.janus.rake_:
    vim_plugin_task "vim-latex", "git://github.com/micheljansen/vim-latex.git"

Then, from inside the Janus installation in  _~/.vim/_ run:
    rake vim-latex

to install vim-latex.

Optionally, add these lines to your _~/.vimrc.local_:
    set grepprg=grep\ -nH\ $*
    
    " OPTIONAL: This enables automatic indentation as you type.
    filetype indent on
    
    " OPTIONAL: Starting with Vim 7, the filetype of empty .tex files defaults to
    " 'plaintex' instead of 'tex', which results in vim-latex not being loaded.
    " The following changes the default filetype back to 'tex':
    let g:tex_flavor='latex'


Using
-----

Just open any .tex file and then in normal mode hit:
  * **\ll** to complile
  * **\lv** to view
  * **\ls** to jump to the current cursor position using synctex


Depending on your configuration, the vim latex suite might require
some additional fiddling in order to work.

If you get stuff like this:

    Error detected while processing function Tex_RunLaTeX:
    line    7:
    E121: Undefined variable: s:target
    E15: Invalid expression: s:target

Remember to set the target (PDF or DVI) in the Tex-Suite menu. 

