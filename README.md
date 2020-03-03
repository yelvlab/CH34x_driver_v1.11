# CH34x_driver_v1.11

> WCH公司的CH34x系列芯片的驱动程序，版本号V1.11


## 原厂驱动包`README.md`

1. BUILDING
 $ sudo make

2. LOAD
 $ sudo make load
 or you can use
 $ sudo insmod ch34x.ko
 
3. UNLOAD
 $ sudo make unload
 or you can use
 $ sudo rmmod ch34x.ko
 
4. AUTOLOAD SINCE BOOT
  $ sudo make install
  
5. CANCEL AUTOLOAD SINCE BOOT
  $ sudo make uninstall
  
Note
  If you wanna look up more details, please open debug switch(DEBUG && VERBOSE_DEBUG) in ch34x.c
  Any question, you can send feedback to mail: tech@wch.cn


## 编译安装方法：

> 测试环境： Ubuntu18.04.3 Desktop
> root权限

0. 安装环境：

```
# apt install git make gcc dkms libelf-dev
```

1. 移除旧驱动文件：

这里用备份的方式代替删除，备份好习惯。

```
# cd /lib/modules/${uname -r}/kernel/drivers/usb/serial/
# mv ch341.ko ch341.ko.backup
```

2. 进入到驱动代码仓库以及编译

请选择合适的仓库存放位置
```
# git clone https://github.com/yelvlab/CH34x_driver_v1.11.git
# cd CH34x_driver_v1.11
# make
```

正常ch340x.c文件编译不会报错，但是不排除其他异常情况，如有错误可以尝试从提示入手解决，或者在issue提出共同学习。

编译成功：
![编译OK](/make_ok.png)

3. 安装驱动:

可以参考官方README内的操作：

```
# make load
```

安装成功：
![安装OK](/make_load_ok.png)
