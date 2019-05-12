# linuxLearning
一些命令啥的

### 1、ps(process status)命令：列出系统中当前运行的那些进程。

使用man ps查看ps手册

ps [options]：

       -A     Select all processes.  Identical to -e.（显示所有进程 （等价于-e））

       -a     Select all processes except both session leaders (see getsid(2)) and processes not associated with a terminal.（显示同一终端下的所有程序）
       
       To see every process on the system using standard syntax:（标准语法）
          ps -e
          ps -ef
          ps -eF
          ps -ely
          
       To see every process on the system using BSD syntax:
          ps ax   显示较详细的资讯
          ps axu  显示所有包含其他使用者的进程的较详细的信息
          
  其实上面这两类指令并没有什么大区别，只是显示的内容有些不同，具体情况使用就行了。

       To print a process tree:（树形显示）
          ps -ejH
          ps axjf

       To get info about threads:（关于线程的信息）
          ps -eLf
          ps axms

### 2、kill指令

  kill [options] <pid>  ：列出一些常用的
       
       HUP     1    终端断线

       INT     2    中断（同 Ctrl + C）

       QUIT    3    退出（同 Ctrl + ）

       TERM    15    终止

       KILL    9    强迫终止

       CONT    18    持续（与STOP相反， fg/bg号令）

       STOP    19    暂停（同 Ctrl + Z）

### 3、ufw（ubuntu firework），参考：https://blog.csdn.net/bigdata_mining/article/details/80699180

linux原始自带防火墙工具iptables，由于过于繁琐，所以ubuntu系统默认提供了一个基于iptable的防火墙工具ufw。

       启用：
       
       sudo ufw enable
       
       sudo ufw default deny
       
运行以上两条命令后，开启了防火墙，并在系统启动时自动开启。关闭所有外部对本机的访问，但本机访问外部正常。

       开启/禁用（端口）：
       
       sudo ufw allow|deny ［service］
       
       如：sudo ufw allow 53  或者  sudo ufw deny smtp
       
       查看防火墙状态：
       
       sudo ufw status
