Fern 文件资源管理器
===================

比 NERDTree
性能好，速度快。仓库地址：https://github.com/lambdalisue/fern.vim

常用操作：

结点

.. code:: text

   l 打开
   e 编辑，同上
   h 关闭

跳转目录，\ ``:cd target_path`` 然后执行 ``Fern .``

.. code:: text

   Backspace 键，回退到上层目录
   enter 切换根节点为光标所在的节点，
   leave 离开当前目录，并进入上一层

文件

.. code:: text

   打开文件
     l 打开
     - 减号键选中
     以右侧鼠标停留的位置做为参考点，可以左右上下分割，上下左右打开 
     上下分割 open:split
     水平左右垂直分割 open:vsplit
       open:top
       open:above
       open:below
       open:left
         open:leftest  最左边
       open:below
       open:right
         open:rightest 最右边
     lcd 使用标签选择并跳转右侧打开的窗口
   创建新文件
     new-file
     n 创建新文件
   复制文件 c
   移动文件 m
   剪切文件 M ，粘贴文件 P
   删除文件
     D 移动到回收站
     remove 直接删除
   显示隐藏文件 !
   文件批量改名, 先用减号键选择中要操作的文件或目录
     R 在新打开的窗口中编辑，完成后 :w 保存，会自动关闭并执行修改文件的命令，不要使用 :wq，不然改名不会成功。

标签

.. code:: text

     open:tabedit    新标签页中打开

执行命令，有些问题，没找到用例

.. code:: text

     ex

书签 https://github.com/lambdalisue/fern-bookmark.vim

.. code:: text

     查看书签 :Fern bookmark:///
     new-leaf 添加书签
     B        添加已选中的节点做为书签
       再次添加选中的书签时才能改名
     D 删除书签（在 :Fern bookmark:/// 下操作）

常见操作

::

   （1）已经用 vim 打开了一个文件，但是想用资源管理器。
        确保当前的 pwd 位置是想要编辑的文件的位置
        :Fern . -drawer -stay
        效果是，左侧打开了一个文件目录树，同时 -stay 保证光标还是停留在原文件中。
        
   （1）在操作要打开的文件时，open 时用 ctrl+d 显示提示
   （3）批量重命名：Shift + V 然后使用 j,k 选中文件，再点 减号 - 确认选中，再点击 R，在新开的窗口中使用 vim 的替换命令进行操作。如将所有文件名中的 abc.com 移除 :%s/abc.com//g
