# TMUX使用

tmux 默认使用 Ctrl-b 作为激活快捷键的开关
 
运行 tmux  
$ tmux
 
显示所有会话  
$ Ctrl-b s  
或者  
$ tmux ls  
 
 
新建会话  
使用 new 命令新建会话，并且该命令允许以参数的形式传递一个会话名。我的建议是在新建时要提供一个会话名以便于日后管理。  
$ tmux new -s session-name  
 
也可以： 不建议  
$ tmux new  
 
 
接入一个之前的会话  
可以简单地输入 tmux a 命令，这样可以接入第一个可用的会话  
$ tmux a  
或者可以通过参数指定一个想接入的会话：  
$ tmux a -t session-name  
   
从会话中断开  
$ tmux detach  
也可以使用快捷键断开会话：  
$ Ctrl-b d  
   
   
关闭会话  
要关闭会话的话，可以使用如下的命令，该命令和接入会话时所使用的命令很像：  
$ tmux kill-session -t session-name  
提示：关闭窗口时也可以使用类似的命令，只不过要把 kill-session 换成 kill-window。另外，还可以使用 tmux killall 同时关闭 tmux。  
 
d  
开启新的窗口  
按下 Ctrl-b 后的快捷键如下：  
? 获取帮助信息  
s 列出所有会话  
$ 重命名当前的会话  
d 断开当前的会话  
   
c 创建一个新窗口  
, 重命名当前窗口  
w 列出所有窗口  
n 选择下一个窗口  
p 选择上一个窗口  
   
h 将光标移入左侧的窗格*  
l 将光标移入右侧的窗格*  
o 在窗格间切换  
x 关闭当前窗格  
   
   
参考：  
[1] Tmux 入门介绍 http://blog.jobbole.com/87278/   
[2] Tmux快捷键 https://gist.github.com/ryerh/14b7c24dfd623ef8edc7  
