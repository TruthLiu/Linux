# 				Linux Prectice

#### 1、获取上周一日期　　date -d 'last-monday' '+%Y-%m-%d'　或　date '+%Y-%m-%d'  --date='last monday'

#### ２、存放用户账号的文件是  /etc/passwd

#### ３、Ｌｉｎｕｘ系统的文件类型：文件，目录，设备，字符，连接



#### 虚拟机与主机连接方式

| 模式    |                                          |
| ----- | ---------------------------------------- |
| 桥接模式  | 宿主机真实网卡和虚拟机的虚拟交换机(vmnet0)是用虚拟桥接模式        |
| NAT模式 | 宿主机vmnet8虚拟网卡与虚拟交换机（vmnet8）之间连接。虚拟交换机与网卡 |
| 仅主机模式 | 宿主机vmnet1虚拟网卡与与虚拟交换机（vmnet1）之间连接         |



#### 软件下载方式：１、二进制发布包　rpm方式和yum方式　源码编译安装　　

#### Ｌｉｎｕｘ内核：用户和软件通讯的平台，系统服务，虚拟内存，io管理，进程管理等。



#### 找出所有用户，和用户ｉｄ，并按照用户ｉｄ的数字顺序排序，输出到文件users.data

#### cat /etc/passwd |cut -d: -f1,3 | sort -t: -k2g >>users.data



#### 统计student.txt文件中共有几个部分，每个部门多少学生：

#### 文件格式：1，tom,男，２４，教学部

#### cut  -d, -f5 student.txt| sort|  uniq -c



#### 编写脚本getday.sh输入一个或多个身份证号，输入你出生的天数：

`if [$# -eq 0]`

` then echo 0` 

` else` 

` for day in $* ` 

`do `

`echo "${day}:$[($(date"+%s")-$(date "+%s" -d ${day:7:8}))/86400]" `

`done `

` fi`

#### 编写一个脚本getMaxMinAvg.sh

```
max=$1
min=$1
sum=0
if [$# -eq 0]
then 
echo 0
else
	for num in $*
	do
		if[$num -gt $max]
		then
			let max=num
		fi
		if[$num -lt $min]
		then
			let min=num
		fi
		let sum+=sum
	done
    echo "max:$max"
    echo "min:$min"
    echo -ne "avg":
    echo "scale=2;$sum/$#"|bc
fi

```

