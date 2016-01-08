# kvmla 配置
web : meteor user
ritter : build user

### 创建一个sudo用户
```bash
# adduser 'ritter'
# adduser ritter sudo 
# adduser ritter root
# adduser ritter ssh
```

### 重新指定语言
```bash
$ sudo apt-get install localepurge
$ sudo locale-gen en_US.UTF-8 zh_CN.UTF-8
$ locale    //查看本地语言
```

### 自动补齐
```bash
$ sudo apt-get install bash-completion
$ sudo apt-get install --reinstall bash-completion
$ cp /etc/skel/.bashrc ~/
$ . ~/.bashrc
```

### 安装fish
```bash
$ sudo install fish
$ fish
```
### update
```
$ sudo apt-get update
E: The method driver /usr/lib/apt/methods/http could not be found.
```
Fixed:
```bash
$ sudo apt-get install apt-transport-https
$ sudo apt-get update
```

### 将程序放到后台运行
```bash
$ nohup meteor &
```




