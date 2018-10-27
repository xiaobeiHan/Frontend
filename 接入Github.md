### 首先标记一下markdown文件的语法： https://www.cnblogs.com/liugang-vip/p/6337580.html ###
# GitHub SSH配置： #
1. 首先检查电脑上是否已经有了SSH Key：
> 运行以下命令：
> cd ~/ .ssh
> ls
如果 id_rsa.pub 或 id_dsa.pub 文件已经存在，就可以跳过步骤2，直接进入步骤3了。
2. （如果本来没有）创建一个SSH Key：
> 运行以下命令
> ssh-keygen -t rsa -C "your_email@example.com"
-t rsa代表的是密钥类型（默认rsa）
接下来会让你输入存储密钥的文件名，推荐直接回撤，不输入文件名
那么就会生成 id_rsa 和 id_rsa.pub 两个秘钥文件。 
> Generating public/private rsa key pair.
> # Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
接着又会提示你输入两次密码（该密码是你push文件的时候要输入的密码，而不是github管理者的密码），
当然，你也可以不输入密码，直接按回车。那么push的时候就不需要输入密码，直接提交到github上了
> Enter passphrase (empty for no passphrase): 
> # Enter same passphrase again:
创建成功后，会有如下提示：
> Your identification has been saved in /c/Users/you/.ssh/id_rsa.
> # Your public key has been saved in /c/Users/you/.ssh/id_rsa.pub.
> # The key fingerprint is:
> # 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@example.com
现在，可以去github上添加公钥了！
3. 添加你的 SSH key 到 github上面去
 > 拷贝id_rsa.pub文件的 全部内容 全部内容 全部内容！到github账号的 设置中，添加SSH Key。
 > title可以不写，或者随便写一个。这个不影响。
4. 测试一下是否添加成功
 > 输入以下代码：
 > ssh -T git@github.com
 > 看到如下警告后，输入yes。再输入密码
 > The authenticity of host 'github.com (207.97.227.239)' can't be established.
 > # RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
 > # Are you sure you want to continue connecting (yes/no)?

 > 最终成功的信号是：
 > Hi username! You've successfully authenticated, but GitHub does not provide shell access.
 5. 恭喜我！开始码代码吧～
 6. 需要注意的是，存放私钥的文件夹 不能给其他用户权限，否则会报错：
  > Permissions 0777 for '/Users/bei/id_rsa' are too open.
  > It is required that your private key files are NOT accessible by others.
  > This private key will be ignored.
  > 解决办法就是 chmod 700 xxx，权限设为私有！
