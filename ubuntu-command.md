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





