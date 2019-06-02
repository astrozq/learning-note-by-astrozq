# 1.运行相关

## 1.1 warnings
设置运行的各类warning状况

https://docs.python.org/3/library/warnings.html

# 2.系统相关

## 2.1 os
该模块使操作系统相关功能的更加便携

https://docs.python.org/3/library/os.html

### 2.1.1 os.open()
    https://www.runoob.com/python/os-open.html

格式：
os.open(file, flags[, mode]);

file -- 要打开的文件

flags -- 该参数可以是以下选项，多个使用 "|" 隔开：

    os.O_RDONLY: 以只读的方式打开
    os.O_WRONLY: 以只写的方式打开
    os.O_RDWR : 以读写的方式打开
    os.O_NONBLOCK: 打开时不阻塞
    os.O_APPEND: 以追加的方式打开
    os.O_CREAT: 创建并打开一个新文件
    os.O_TRUNC: 打开一个文件并截断它的长度为零（必须有写权限）
    os.O_EXCL: 如果指定的文件存在，返回错误
    os.O_SHLOCK: 自动获取共享锁
    os.O_EXLOCK: 自动获取独立锁
    os.O_DIRECT: 消除或减少缓存效果
    os.O_FSYNC : 同步写入
    os.O_NOFOLLOW: 不追踪软链接
    
mode -- 设置权限等操作

### 2.1.2 os.path()
 可进行路径操作，如返回绝对路径、基本名称等

https://docs.python.org/3/library/os.path.html#module-os.path


os.path.exists(path)

    判断路径是否存在

Return True if path refers to an existing path or an open file descriptor. Returns False for broken symbolic links. On some platforms, this function may return False if permission is not granted to execute os.stat() on the requested file, even if the path physically exists.

