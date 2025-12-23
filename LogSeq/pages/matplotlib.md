- ```python
  import matplotlib.pyplot as plt
  %matplotlib inline #在jupyter内显示图片
  plt.plot(x,y) #x,y是函数线的x和y值
  plt.scatter(x,y)#一样，画散点图
  plt.hlines(0,0,6)#画横线，可以指定起始位置和高度
  plt.bar(x,y)#画柱状图
  
  ```