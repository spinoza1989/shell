# shell

shebang机制

#!/bin/bash



### 执行

- bash + 脚本文件名

- 加执行权限 ， 用绝对路径执行/或者加. 用相对路径执行
- 加执行权限，把命令所在的路径加入到path变量里面





### 脚本总结

- 查看系统信息

~~~
#!/bin/bash
lscpu | sed -nE 's/^Model name: +(.*)/\1/p'
head -n1 /proc/meminfo
lsblk /dev/vda | grep "^vda" | tr -s " "| cut -d " " -f4
cat /etc/os-release  | sed -nr "s/^NAME=\"(.*)\"/\1/p"
~~~



















