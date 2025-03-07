另存为
####################################

在 VIM 中，保存和另存为的命令都是 ``:w`` ，只是在另存为的时候需要指定路径和文件名。


基本操作
************************************

1. 如果只指定文件名，那么会在默认路径下保存文件。可以使用 ``:pwd`` 查看默认路径。

.. highlight:: none

::

    :w name.txt


.. hint:: 修改默认路径为打开文件的路径

    另存为文件的路径一般都会与原文件路径一致，如果文件的路径层级比较多，每次都输入路径会很麻烦而且低效。可以在 ``~/.vimrc`` 配置文件中加入以下配置，使每次启动 vim 时，默认路径都为打开文件的路径。

    ::

        exec 'cd' '%:p:h'

2. 指定另存为的路径和文件名，路径必须已经创建。

::

    :w ~/Documents/name.txt

3. 将文件的指定行数另存为。

::

    :15,49 w name.txt

4. 将选中的内容另存为。

::

    :'<,'>w name.txt

4. 将文件的指定行数追加到原有文件的最后。

::

    :15,49 w >> name.txt
