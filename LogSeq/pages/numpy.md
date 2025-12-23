- numpy是一个常用数值计算模块，提供了数值计算数组numpy.ndarray这一数据类型
- 初始化
	- ```python
	   # 由普通数组初始化
	  import numpy as np
	  np.array([[1,2],[3,4]])
	  
	  np.ones([3,2])
	  np.zeros([3,2])
	  np.arange(0,1,0.1)
	  np.arange(0,1,0.1).reshape(2,5)
	  
	  b=a #引用不是拷贝
	  
	  
	  ```
- metadata
	- ```python
	  import numpy as np
	  a=np.array([[1,2],[3,4],[5,6]])
	  a.ndim #2维
	  a.shape # (3,2)
	  a.size #6=3*2
	  a.dtype #基本数据类型
	  
	  ```
- 引用
	- ```python
	  import numpy as np
	  a=np.array([[1,2],[3,4],[5,6]]).transpose()
	  a[1,2]
	  a[1,:]
	  a[1,1:]
	  a[1,:1]
	  a[1,:-1]
	  a>3 # [False,False,False,True,True,True] 先拍扁成一维，然后向量化执行运算a>3
	  a>3 & b<2 #拍扁成一维，一个一个对位计算与&,得到一个[False, False,False,False,True,True]
	  			#标记出所有的i:a[i]>3 且b[i]<2
	  a[a>3] # [4,5,6]按值的条件引用 
	  a[a%2==0] #数组中 所有偶数
	  #以上引用都可以取值和赋值
	  ```
- 数组操作
	- ```python
	  x=np.zeros(10)
	  x=np.append(x,10)#尾部填上一个10
	  x=np.insert(x,4,7.8) #4号位插入7.8
	  x=np.delete(x,-1) #末尾删除
	  x=np.unique(x)#数组去重
	  ```
- 运算
	- ```python
	  #有些操作只能对一维数组，可以操作完以后再reshape
	  np.arange(10,11,0.1).reshape(2,5)
	  #连接两个数组x,y，连接对第一维连接，所以第一个维度的大小可以不同，其他所有维度的大小必须相同
	  np.concatenate(x,y)
	  #向量化运算，内置函数可以自发对每个数组元素进行计算
	  np.sin(np.arange(10,11,0.1).reshape(2,5))
	  #自定义函数需要向量化算子过后才能对数组向量化计算
	  my_fun_v=np.vectorize(my_fun)
	  my_fun_v(np.arnage(10,11,0.1))
	  #点乘
	  x.dot(y)
	  ```
-