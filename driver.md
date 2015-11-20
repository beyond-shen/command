## 读设备文件
```
$ sudo insmod hello.ko
$ cat /dev/hello
$ sudo rmmod hello
```

## 写设备文件
```
$ sudo insmod hello.ko
$ sudo chown linux:linux /dev/hello
$ echo "Welcome to kernel" > /dev/hello
$ sudo rmmod hello
```

## 查看设备号
查看当前系统设备已使用的设备号, 包括字符设备和块设备.
```
$ cat /proc/devices
```


## 管道操作

需要保证在同一个目录下.

### 窗口-1
1. 创建管道文件.
```
$ mkfifo ps
``` 
2. 用cat读ps
```
$ cat ps
``` 
### 窗口-2
1. 向ps写数据
```
$ cat > ps
``` 
