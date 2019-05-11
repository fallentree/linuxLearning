# linuxLearning
一些命令啥的

### 1、ps(process status)命令：列出系统中当前运行的那些进程。

使用man ps查看ps手册

ps [options]：

SIMPLE PROCESS SELECTION
       a      Lift the BSD-style "only yourself" restriction, which is imposed upon the set of all processes when some BSD-style (without "-") options are used or when the ps personality setting is
              BSD-like.  The set of processes selected in this manner is in addition to the set of processes selected by other means.  An alternate description is that this option causes ps to list
              all processes with a terminal (tty), or to list all processes when used together with the x option.

       -A     Select all processes.  Identical to -e.

       -a     Select all processes except both session leaders (see getsid(2)) and processes not associated with a terminal.

       -d     Select all processes except session leaders.

       --deselect
              Select all processes except those that fulfill the specified conditions (negates the selection).  Identical to -N.

       -e     Select all processes.  Identical to -A.

       g      Really all, even session leaders.  This flag is obsolete and may be discontinued in a future release.  It is normally implied by the a flag, and is only useful when operating in the
              sunos4 personality.

       -N     Select all processes except those that fulfill the specified conditions (negates the selection).  Identical to --deselect.

       T      Select all processes associated with this terminal.  Identical to the t option without any argument.

       r      Restrict the selection to only running processes.

       x      Lift the BSD-style "must have a tty" restriction, which is imposed upon the set of all processes when some BSD-style (without "-") options are used or when the ps personality setting
              is BSD-like.  The set of processes selected in this manner is in addition to the set of processes selected by other means.  An alternate description is that this option causes ps to
              list all processes owned by you (same EUID as ps), or to list all processes when used together with the a option.

PROCESS SELECTION BY LIST
       These options accept a single argument in the form of a blank-separated or comma-separated list.  They can be used multiple times.  For example: ps -p "1 2" -p 3,4

       -123   Identical to --pid 123.

       123    Identical to --pid 123.

       -C cmdlist
              Select by command name.  This selects the processes whose executable name is given in cmdlist.

       -G grplist
              Select by real group ID (RGID) or name.  This selects the processes whose real group name or ID is in the grplist list.  The real group ID identifies the group of the user who created
              the process, see getgid(2).

       -g grplist
              Select by session OR by effective group name.  Selection by session is specified by many standards, but selection by effective group is the logical behavior that several other
              operating systems use.  This ps will select by session when the list is completely numeric (as sessions are).  Group ID numbers will work only when some group names are also specified.
              See the -s and --group options.

