vim-plug 插件管理器
####################################

::

   :e $MYVIMRC           # 在家目录下创建 .vimrc, 默认没有, 然后粘贴自己的配置。

插件 Vim-Plug https://github.com/junegunn/vim-plug (安装方法有问题)

根据 unix 安装 Vim-Plug 的命令：（仅适用于真的 Linux，树莓派 debian
中可用）

.. code:: shell

   curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

这个命令执行在 cygwin shell 中没有效果。

cygwin shell 中用这个方法去安装：

.. code:: shell

   % mkdir -p ~/.vim/autoload
   % cd ~/.vim/autoload
   % wget https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

一行代码安装：

.. code:: shell

   mkdir -p ~/.vim/autoload && cd ~/.vim/autoload && wget https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

在 ``vimrc`` 最后添加:

.. code:: vimscript

   " Plugins {{{
   " PlugInstall! and PlugUpdate
   call plug#begin('~/.vim/plugged')

   " Plug 'yianwillis/vimcdoc'     " vim 中文文档
   " Plug 'scrooloose/nerdtree'    " nerdtree

   " Initialize plugin system
   set rtp+=~/.vim/

   call plug#end()
   " Plugins_end }}}

这命令只是下载一个文件 ``plug.vim`` 然后放到 ``~/.vim/autoload``
下，没有对应文件夹就新建。

最后进入 Vim, 使用 PlugInstall 进行具体的插件安装:

.. code:: shell

   vim
   :PlugInstall
