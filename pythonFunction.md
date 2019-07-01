# 1.运行相关函数包

## 1.1 warnings
设置运行的各类warning状况

https://docs.python.org/3/library/warnings.html


## 1.2 sys
该模块可供访问由解释器使用或维护的变量和与解释器进行交互的函数。
### 1.2.a 常用方法
https://www.zhihu.com/question/31843617

    sys.argv 命令行参数List，第一个元素是程序本身路径
    sys.modules.keys() 返回所有已经导入的模块列表
    sys.exc_info() 获取当前正在处理的异常类,exc_type、exc_value、exc_traceback当前处理的异常详细信息
    sys.exit(n) 退出程序，正常退出时exit(0)
    sys.hexversion 获取Python解释程序的版本值，16进制格式如：0x020403F0
    sys.version 获取Python解释程序的版本信息
    sys.maxint 最大的Int值
    sys.maxunicode 最大的Unicode值
    sys.modules 返回系统导入的模块字段，key是模块名，value是模块
    sys.path 返回模块的搜索路径，初始化时使用PYTHONPATH环境变量的值
    sys.platform 返回操作系统平台名称
    sys.stdout 标准输出
    sys.stdin 标准输入
    sys.stderr 错误输出
    sys.exc_clear() 用来清除当前线程所出现的当前的或最近的错误信息
    sys.exec_prefix 返回平台独立的python文件安装的位置
    sys.byteorder 本地字节规则的指示器，big-endian平台的值是'big',little-endian平台的值是'little'
    sys.copyright 记录python版权相关的东西
    sys.api_version 解释器的C的API版本

### 1.2.b 区别
#### 与os
os模块负责程序与操作系统的交互，提供了访问操作系统底层的接口;sys模块负责程序与python解释器的交互，提供了一系列的函数和变量，用于操控python的运行时环境。

## 1.3 isinstance
https://www.runoob.com/python/python-func-isinstance.html

isinstance() 函数来判断一个对象是否是一个已知的类型，类似 type()。

isinstance() 与 type() 区别：

type() 不会认为子类是一种父类类型，不考虑继承关系。

isinstance() 会认为子类是一种父类类型，考虑继承关系。

如果要判断两个类型是否相同推荐使用 isinstance()。

# 2.系统相关函数包及文件工具

## 2.1 os
该模块使操作系统相关功能的更加便携，向python提供运行环境

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


### 2.1.a 常用总结
https://www.zhihu.com/question/31843617

    os.remove() 删除文件
    os.rename() 重命名文件
    os.walk() 生成目录树下的所有文件名
    os.chdir() 改变目录
    os.mkdir/makedirs 创建目录/多层目录
    os.rmdir/removedirs 删除目录/多层目录
    os.listdir() 列出指定目录的文件
    os.getcwd() 取得当前工作目录
    os.chmod() 改变目录权限
    os.path.basename() 去掉目录路径，返回文件名
    os.path.dirname() 去掉文件名，返回目录路径
    os.path.join() 将分离的各部分组合成一个路径名
    os.path.split() 返回( dirname(), basename())元组
    os.path.splitext() 返回 (filename, extension) 元组
    os.path.getatime\ctime\mtime 分别返回最近访问、创建、修改时间
    os.path.getsize() 返回文件大小
    os.path.exists() 是否存在
    os.path.isabs() 是否为绝对路径
    os.path.isdir() 是否为目录
    os.path.isfile() 是否为文件

## 2.2 glob
用来查找匹配的文件 https://docs.python.org/3/library/glob.html 

e.g. https://www.cnblogs.com/hongten/p/hongten_python_glob.html

    *    :   匹配所所有
    ?    :   匹配一个字符
    *.*  :   匹配如：[hello.txt,cat.xls,xxx234s.doc]
    ?.*  :   匹配如：[1.txt,h.py]
    ?.gif:   匹配如：[x.gif,2.gif]


# 3. 优化工具
## 3.1 operator
一种基于c语言的运行高效的，可用来代替默认运算符的计算函数
具体参见 https://docs.python.org/3/library/operator.html

## 3.2 intertools
能够高效循环创建迭代器的函数

注：itertools模块提供的全部是处理迭代功能的函数，它们的返回值不是list，而是迭代对象，只有用for循环迭代的时候才真正计算。 https://www.liaoxuefeng.com/wiki/897692888725344/983420006222912

## 3.3 multiprocessing
并行计算函数 https://docs.python.org/3/library/multiprocessing.html#module-multiprocessing

### 3.3.1 Pool
Pool模块是用来创建管理进程池的，当子进程非常多且需要控制子进程数量时可以使用此模块。 https://thief.one/2016/11/24/Multiprocessing-Pool/


# 4.简化工具
## 4.1 collections
collections是Python内建的一个集合模块，提供了许多有用的集合类。 https://www.liaoxuefeng.com/wiki/897692888725344/973805065315456

### 4.1.1 OrderDict
使用dict时，Key是无序的。在对dict做迭代时，我们无法确定Key的顺序。
如果要保持Key的顺序，可以用OrderedDict

# 5.计算工具
## 5.1 numpy
不解释


### 5.1.1 numpy.linspace
numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None)
在指定的间隔内返回均匀间隔的数字。

### 5.1.2 numpy.rad2deg
numpy.rad2deg(x, /, out=None, *, where=True, casting='same_kind', order='K', dtype=None, subok=True[, signature, extobj]) = <ufunc 'rad2deg'>

从弧度转变为角度（2→to，好冷）

扩展：deg2rad —— 从角度转变为弧度

### 5.1.3 numpy.zeros
numpy.zeros(shape, dtype=float, order='C')
返回一个所有项填充为0的相应类型的数组

eg

    >>> s = (2,2)
    >>> np.zeros(s)
    array([[ 0.,  0.],
       [ 0.,  0.]])

### 5.1.4 numpy.isscalar¶
numpy.isscalar(num)
如果是标量类型，返回True




## 5.2 scipy
不解释

## 5.3 pandas
不解释

## 5.4 h5py
HDF（Hierarchical Data Format）指一种为存储和处理大容量科学数据设计的文件格式及相应库文件。当前流行的版本是 HDF5。

h5py就是处理HDF5数据的。另外还有PyTables。可以与NumPy联动。 http://www.h5py.org/

## 5.5 rpy2
使R在python中运行 https://rpy2.readthedocs.io/en/version_2.8.x/


# 6.画图工具
## 6.1 matplotlib
东西太多，不太想说
### 6.1.1 matplotlib.use
选择渲染和GUI工具 https://matplotlib.org/api/matplotlib_configuration_api.html?highlight=use#matplotlib.use

### 6.1.2 mpl_toolkits.basemap
地图绘制工具 https://matplotlib.org/basemap/ https://www.cnblogs.com/vamei/archive/2012/09/16/2687954.html


## 6.2 seaborn
统计数据可视化包 http://seaborn.pydata.org/

## 6.3 spherical_geometry
球面几何 

# 7.天文相关
## 7.1 astropy

## 7.2 spherical_geometry
球面几何包，用于处理天空任意区域的球形多边形

好像是pyraf和stsci的东西
github和astropy这边也有东西，相比之下可能更靠谱一些 https://spacetelescope.github.io/spherical_geometry/spherical_geometry/ https://github.com/spacetelescope/spherical_geometry

## 7.3 PyXspec
X射线光谱分析包Xspec的python版

# 8.杂类

