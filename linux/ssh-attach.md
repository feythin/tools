1.把 eval `/usr/local/bin/ssh-attach` 复制到文件 /home/用户名/.bashrc 下。

2. 执行 source .bashrc ，输入你自己的口令（也就是passphrase）

3.直接ssh ip 登陆应用服务器。

example:

# 1.在/home/feiyul/.bashrc文件末尾添加 eval `/usr/local/bin/ssh-attach`
[feiyul@l-rtools2.ops.cn2 ~]$ cat /home/feiyul/.bashrc
# .bashrc
 
# Source global definitions
if [ -f /etc/bashrc ]; then
    . /etc/bashrc
fi
 
# User specific aliases and functions
eval `/usr/local/bin/ssh-attach`
 
 
# 2. source 文件
[feiyul@l-rtools2.ops.cn2 ~]$ source /home/feiyul/.bashrc
Enter passphrase for /home/feiyul/.ssh/id_rsa:                         (此处需要输入你密钥密码）
Identity added: /home/feiyul/.ssh/id_rsa (/home/feiyul/.ssh/id_rsa)
Agent pid 27258
[feiyul@l-rtools2.ops.cn2 ~]$
 
 
# 3.直接登陆服务器
[feiyul@l-rtools2.ops.cn2 ~/.ssh]$ ssh l-ng1.ops.cn1
Last login: Mon Jun  4 12:15:56 2018 from 172.31.90.46
[feiyul@l-ng1.ops.cn1 ~]$
