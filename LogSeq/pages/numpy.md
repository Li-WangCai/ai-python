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
	  a[a>3] # [4,5,6]按值的条件引用 
	  #以上引用都可以取值和赋值
	  ```
- 数组操作
	- ```python
	  x=np.zeros(10)
	  x=np.append(x,10)#尾部填上一个10
	  x=np.insert(x,4,7.8) #4号位插入7.8
	  x=np.delete(x,-1) #末尾删除
	  
	  ```
- 运算
	- ```python
	  ```
-