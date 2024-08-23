# shell

shebang机制

#!/bin/bash



### 执行

- bash + 脚本文件名

- 加执行权限 ， 用绝对路径执行/或者加. 用相对路径执行
- 加执行权限，把命令所在的路径加入到path变量里面





### 脚本总结

- 查看系统信息

~~~shell
#!/bin/bash

colored_echo() {
    local text="$1"
    local color="$2"

    # 定义颜色代码
    case "$color" in
        "red")    color_code="\033[31m" ;;  # 红色
        "green")  color_code="\033[32m" ;;  # 绿色
        "yellow") color_code="\033[33m" ;;  # 黄色
        "blue")   color_code="\033[34m" ;;  # 蓝色
        "magenta")color_code="\033[35m" ;;  # 品红色
        "cyan")   color_code="\033[36m" ;;  # 青色
        "white")  color_code="\033[37m" ;;  # 白色
        *)        color_code="\033[0m" ;;   # 默认颜色（无色）
    esac

    # 输出带颜色的字符串
    echo -e "${color_code}${text}\033[0m"
}

echo -e "CPU: \c"
colored_echo "$(lscpu | sed -nE 's/^Model name: +(.*)/\1/p')" "yellow"
head -n1 /proc/meminfo | tr -s " "
echo -e "/dev/vda: \c"
colored_echo "$(lsblk /dev/vda | grep "^vda" | tr -s " "| cut -d " " -f4)" "yellow"
echo -e "OS-Name: \c"
colored_echo "$(cat /etc/os-release  | sed -nr "s/^NAME=\"(.*)\"/\1/p")" "yellow"

~~~





















