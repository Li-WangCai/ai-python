- 初始化
	- ```python
	  x=[1,2,3,4]
	  x[0] #1
	  x.append(99)
	  #x=[1,2,3,4,99]
	  x=list({1,2,3,4}) #x=[1,2,3,4]
	  x=list(range(1,5,1)) #x=[1,2,3,4]
	  
	  
	  ```
- 增删
	- ```python
	  x=[1,2,3,4]
	  x.append(5) #x=[1,2,3,4,5]
	  y=x.pop() #y=3,after this line, x=[1,2,3,4]
	  
	  x=[1,2,3,4]
	  del x[0] # now x=[2,3,4]
	  ```
- 访问元素
	- ```python
	  x=[0,1,2,3,4]
	  x[0] #0
	  x[1] #1
	  x.pop()# 4, after than x=[0,1,2,3]
	  x[1:] # [1,2,3]
	  x[1:2] # [1,2]
	  x[:2] # [0,1,2]
	  x[:-1] #[0,1,2]
	  
	  a=[[1,2,3],[4,5,6]]
	  [x for x,y,z in a] #[1,4]
	  ```
- 列表解析
	- ```python
	  [x^2 for x in range(100) if x%7==0]
	  ```
- 是否存在某个元素
	- ```python
	  3 in [1,2,3]  # True
	  4 in [1,2,3]  # False
	  3 not in [1,2,3] #False
	  ```
- 连接列表
	- ```python
	  '_'.join(['abc','def']) #abc_def
	  ```
- 拆分列表
	- ```python
	  'abc_def'.split('_') # ['abc','def']
	  ```
- 排序列表
	- ```python
	  a=[['a',1],['b',2],['c',3]]
	  sorted(a,reverse=True,key=lambda x:x[1])
	  ```