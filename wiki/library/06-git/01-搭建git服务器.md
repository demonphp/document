### 搭建git服务器

1、安装：
```shell
yum install -y git
```
2、创建一个git用户用来运行git服务
```shell
adduser git  
```

3、初始化git仓库
```shell
git init --bare learngit.git
chown git:git learngit.git  
```

4、客户端clone一下远程仓库
```shell
git clone git@112.74.184.54:/lnmp/gitbrowser/learngit.git
```

5、创建SSH Key (id_rsa和id_rsa.pub)
```shell
ssh-keygen -t rsa -C "www@demon.com"
```


6、Git服务器打开RSA认证   
```shell
vim /etc/ssh/sshd_config
RSAAuthentication yes    
PubkeyAuthentication yes     
AuthorizedKeysFile  .ssh/authorized_keys
执行
git clone git@192.168.8.34:/data/git/learngit.git
```

7、禁用git用户的shell登陆
```shell
git:x:1001:1001:,,,:/home/git:/bin/bash  
最后一个冒号后改为：
git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell  
```
