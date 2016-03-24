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


## 安装ShadowSocks
简介`Shadowsocks`安装配置过程。

### ubuntu 安装方法

```
 $ sudo apt-get update 
 $ sudo apt-get install python-pip
 $ sudo apt-get shadowsocks
```
### 配置文件
需要在`/etc/`目录下创建一个`shadowsocks.json`的文件, 配置文件内容如下:
```
{
    "server":"my_server_ip",
    "server_port":8388,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"mypassword",
    "timeout":300,
    "method":"rc4-md5"
}
```
各字段的含义：

|name	|info|
| :------ | :--------------------------------: |
|server	|服务器 IP (IPv4/IPv6)，注意这也将是服务端监听的 IP 地址|
|server_port|	服务器端口|
|local_port|	本地端端口|
|password|用来加密的密码|
|timeout|	超时时间（秒）|
|method|加密方法，"rc4-md5"|

### 运行方法
如果想直接在命令行下运行, 如果要停止运行，将命令中的start改成stop。

```
$ sudo ssserver -c /etc/shadowsocks.json -d start
```

### 配置开机自启动

```
$ sudo chmod 755 /etc/shadowsocks.json
$ sudo apt–get install python–m2crypto   //安装支持算法的库
```
需要将启动项增加到, 启动文件中.
```
$ sudo vi /etc/rc.local

/usr/local/bin/ssserver –c /etc/shadowsocks.json
```


# Ubuntu config

## 语言设置
如果没有设置好语言启动不了`meteor`, 会显示`mongoDB`服务启动失败.

解决方法如下:
```
$ sudo apt-get install locales
$ sudo locale-gen en_US.UTF-8
$ sudo localedef -i en_GB -f UTF-8 en_US.UTF-8 
```
