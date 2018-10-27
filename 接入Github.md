### 首先标记一下markdown文件的语法： https://www.cnblogs.com/liugang-vip/p/6337580.html
# GitHub SSH配置：
1. 首先检查电脑上是否已经有了SSH Key：
>  运行以下命令：
### cd ~/ .ssh
### ls
### 如果 id_rsa.pub 或 id_dsa.pub 文件已经存在，就可以跳过步骤2，直接进入步骤3了。
2. （如果本来没有）创建一个SSH Key：
> 运行以下命令
### ssh-keygen -t rsa -C "your_email@example.com"