<b><font color=Violet></font></b>


# GBM_catalog_spectralanalysis_lib.py

#Classes for skymap 
## class GBM_detector --57
1. 获取卫星位置的四元数 --69
2. 获取各探头的四元数(? --78)
3. 获取各探头的探测范围 --91
4. 绘制范围 --99
5. 绘制源点（？） --104

## class 各探头位置 --(111-221)
## class GBMtime --224
对探测时间做出限制

(229-243） utc_tt_diff ————闰秒

## class GBM --267
开始调用时间和位置

1. 确认源是否存在
2. 获取源和探测器的中心点、范围、四元数
3. 获取地球坐标
4. 通过地球与费米卫星位置绘制地球遮挡范围
5. 绘制图像的函数

<b>separation</b> 返回源与各探头之间的夹角 --360

## SOME FUNCTIONS

### def open_fit （485）

<b>(485-495)__fits格式的读取方式问题，以及qsj1-4是什么</b>

### def find_right_list （497）

判断列表的时间是否是该GRB发生前后

met--涉及闰秒问题的时间

### def met2utc_shao
emmm

# Tips

1. jar ——软件包文件格式，用于java类文件及相关元数据好文本图片等，类似zip

2. @classmethod 类方法，可在无实例的情况下直接使用类，具体定义参考 https://www.cnblogs.com/wangyongsong/p/6750454.html#_label2  实例可参考 https://www.zhihu.com/question/20021164

3. Python 字典(Dictionary) keys() 函数以列表返回一个字典所有的键。 https://www.runoob.com/python/att-dictionary-keys.html
e.g.
 
    dict.keys()

4. 
