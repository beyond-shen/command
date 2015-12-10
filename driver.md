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

## 查看kernel连接符号表
```
$ cat /proc/kallsyms
```

## 查看设备号
查看当前系统设备已使用的设备号, 包括字符设备和块设备.
```
$ cat /proc/devices
```
## 查看中断
第一列是中断号, 第二列是接收中断数目的计数器. 第三列是中断的中断控制器.第四列是中断相关的设备名子.
```
$ cat /proc/interrupts
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




# 字符驱动模型
	1. __init
		1. 设备号(主, 次设备号)
			1. 设备号是由主,次设备号拼接而成.
			2. 主,次设备号的拼接(高12位为主设备号, 低20位为次设备号)
			3. register_chrdev_region().
			4. 字符设备号存储在哈希表中.
			5. 主设备1~255, 次设备0~255.
		2. 注册设备
			1. 初始化cdev结构体.
				1. 给.owner = THIS_MODULE
				2. 给.fops = file_operations
				3. 给.name = 设备字
				4. 给.count = 设备数量
				5. 给.dev = 设备号
			2. 将cdev加入由系统维护的字符设备双向循环链表中.
	2. __exit
		1. device_destroy();
		2. class_destroy();  udev
		3. cdev_del()
		4. unregister_chrdev_region()
	3. 模块宏-> license, 作者, 描述.
	4. file_operations结体
	5. open()函数方法 -> 自旋锁()
	6. read()函数方法 -> 返回值为0表示EOF. 标记读的偏移量. 
	7. write()函数方法 -> 标记写的偏移量.
	8. ioctl()函数方法 -> _IO: 1.nr(0~7) 2:type(8~15) 3.size(16~29) 4.dir(30~31)
	                      _IOR
	                      _IOW
	                      _IORW
	9. release()函数方法 -> 应用close()
	10. 自动创建设备节点.
	    1. class_create(THIS_MODULE, "hello") -> /sys/class/hello
	    2. device_create("led")   -> /dev/led

## misc:
	1. misc_register() -> 注册misc设备到miscedevice结构体中
	2. misc_unregister() -> 注销misc设备
	3. misc_init()  -> misc设备初始化
		1. 申请设备号, 主10, 次0, 数量 256
		2. 注册misc设备到字符设备双向循环链表中.
		3. file_operations -> open()
	4. misce_open()
		1. 使用次设备号,在miscdevice结构体中, 查找misc设备.
		2. 用misc设备中的fops替换file结体中的fops方法.
		3. 调用misc设备中实现的file_operations中open方法.

## 数据结构:
	1. 单向链表 (设备号)
	2. 双向循环链表
		1. container_of()
		2. list_for_each() 



























