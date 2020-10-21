# Applications of Deep Neural Networks
* 主要来自Jeff_Heanton的Washington University (in St. Louis) Course T81-558: Applications of Deep Neural Networks
* 原代码、文本可直接到GitHub上寻找，或通过Part1.1页面中的链接也可。
***
## 1. Part1 : Python基础与文件读取
* Part1.1 : 课程概览
* Part1.2 : Python介绍
  * 如何确保使用的TensorFlow版本、判断是否正在使用CoLab
  * print()语句的使用：使用f-string打印、
  * if语句的使用
  * loop语句的使用
* Part1.3 : Python中的列表、字典、集合和JSON数据类型
  * 列表和元组的异同、遍历集合中的元素
  * 列表的添加append()、插入insert()、删除remove()、del list[x]
  * 集合与元组、列表的异同
  * 集合的添加add()
  * 字典和JSON的异同
  * zip():将两个列表对应元素合并成一个个元组
  * enumerate():返回一个列表每个元素对应的索引和元素
  * JSON类型的简单介绍
* Part1.4 : 文件处理
  * 一般需要学会处理的文件类型
  * 读取CSV文件
  * 流式读取CSV文件(适用于大规模数据)
  * 读取text文件
  * 读取图片
* Part1.5 : Python的函数、常用的函数(Lambdas、Map、Reduce)
  * 函数的基本创建
  * map():输入一个函数和一个列表，将列表的每个值都放入函数，返回经过函数处理后的列表
  * filter():输入一个函数和一个列表，将列表的每个值都放入函数，返回为True的值
  * lambda : 一个匿名函数，可自己百度语法
  * reduce():输入一个函数和一个列表，用传给 reduce() 中的函数 function（有两个参数）先对集合中的第 1、2 个元素进行操作，得到的结果再与第三个数据用 function 函数运算，最后得到一个结果。

## 2. Part2 : Pandas处理数据、提取特征
* Part2.1 : Pandas介绍
  * 加载数据:pd.read_csv()
  * 处理数据:
    * 缺失值的处理：一般使用中位数来填充
    * 离群值的处理: 一般删除即可df.drop()
    * 无用域的处理: 对于没有价值的列可以直接删除
    * 连接行或列: pd.concat()
    * Dataframe转换为Martix类型:df[...].values
    * Dataframe保存为CSV类型文件:df.to_csv()
    * Dataframe保存为Pickle类型文件:pickle.dump(df,fp)
  * 使用Dataframe数据生成：训练集和验证集
* Part2.2 : Dataframes中的分类值和连续值
  * 编码连续值: z-score
  * 编码分类值: 
    * 设置为虚拟变量(独热编码one-hot-encoding): pd.get_dummies()
    * 设置为目标编码(计算类别的平均目标价值:根据标签值来改变训练值，很容易过拟合！)
    * 设置为顺序值：如有等级区分的分类值
* Part2.3 : Dataframes中的分组、排序、混洗
  * 混洗数据集:df.reindex(np.random.permutation(df.index))、df.reset_index()
  * 排序数据集:df.sort_values()
  * 分组数据集:df.groupby()、df.groupby(column_name)[column_name].mean().to_dict()、mean换成count也可
* Part2.4 : Dataframes中的map()、apply()
  * df[].map(dict):一般是针对df中某一列的数据进行映射到map中dict的value
  * df.apply(function,axis):针对df的全部数据的每一行或每一列输入到function中进行计算，并且返回新的df
  * 在特征工程中使用map(),apply():一个csv文件处理获得新特征的例子
* Part2.5 : 特征工程的实例
  * 重量单位的转换
  * 地区经纬度及其距离计算(使用的是Google的API，未实现)

## 3. Part3:
* Part3.1 : 神经网络与深度学习的介绍
  * 分类和回归模型
  * 神经元和层
  * 神经元、层的类型
    * 输入、隐藏、输出、上下文、偏置神经元
    * 输入、输出、隐藏层
  * 为什么需要偏置神经元:思考有偏置、无偏置激活函数的区别！(简单画图即可明了)
  * 现代激活函数：
    * ReLu、Softmax、Linear
  * 经典激活函数:
    * Step、Sigmoid、Hyperbolic Tangent
  * 为什么ReLu更有效:考虑导数变化的区别！
