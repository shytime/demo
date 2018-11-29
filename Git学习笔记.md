<center>Git学习笔记</center>

## 快捷键

shift+insert  =粘贴

CTRL+c 强制退出

\ 不间断

## vim的模式操作

:i 进入编辑模式

Esc 回到普通模式

:q！放弃保存并退出

:wq  退出并保存

 jj顶端

J 底端

k 往上走

j 往下走





## 命令

git show 查看不同历史版本的文件

git status 

git add

git commit -m "备注"

git log 历史版本消息

cat 进入文件

cd .. 进入上一级

vim 编辑文件

git remote add origin http://github.com/shytime/demo 连接远程仓库

vim 编辑器

mkdir+目录名    创建目录make directory

cd+目录名          进入目录 change directory

pwd 打印当前工作目录 print working directory

mv 移动文件 move

rm + 文件名     删除 remove

cp a.txt b.txt   复制 copy  把a.txt复制为b.txt

echo ‘文字’   打印文字

echo 'hello'  > a.txt   把hello放入a.txt这个文件

ls 查看

ls.. 查看上级目录

mv b.text ../b.txt 把b.txt移到上级文件夹

mv a.txt c.txt 文件重命名  （a.txt改为c.txt）

git config --list #显示当前的git配置

git config --global user.name '名字‘

git config --global user.email '邮箱‘

~ 主目录

list -a 查看隐藏目录

vim git config 编辑配置文件

git commit -am '' 同时add commit







## Git远程推送

git remote -v 查看有没有与远程仓库连接

git push origin master 把本地仓库推送到github

git add . 把所有文件提交到暂存区

git clone http://github.com/

git commit -a -m '修改了后的文件'

git pull origin master 把远程仓库推到本地仓库 





**注意事项**：首先 git add 提交上暂存区

再 git commit 提交上本地仓库

最后 git push 推上github







