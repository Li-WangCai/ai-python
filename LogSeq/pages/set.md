- 初始化
	- ```python
	  a={1,2,3}
	  
	  x=[1,2,3]
	  a=set(x) #转化列表成为集合
	  
	  x=set()
	  x.add(a)
	  x #{2}
	  
	  ```
- 运算
	- ```python
	  a={1,2,3}
	  b={3,4,5}
	  
	  1 in a # True  判断是否元素
	  a|b # 并集
	  a&b #交集
	  {1,2}<=a # True  子集
	  a-b #差集
	  a.update(b) #将b集合并入a
	  a.remove(1) #删除元素
	  
	  from itertools import combinations
	  list(combinations(x,2)) #组合
	  ```