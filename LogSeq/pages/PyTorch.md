- basic
	- ```python
	  import torch
	  #基本数据结构式torch array
	  #可以直接生成
	  x=torch.ones(5,3,dtype=torch.float64)
	  torch.manual_seed(2)
	  x=torch.randn(4,4)
	  #可以从numpy转换
	  x=torch.from_numpy(numpy.random.randn(5,3))
	  #可以转换到numpy
	  x.numpy()
	  #到list
	  x.tolist()
	  #meta data
	  #元素个数
	  x.numel()
	  #访问元素
	  x[:,1]
	  #通过新view改变行列
	  y=x,view(-1,1)
	  y.shape #引用
	  #运算
	  #加法
	  x=torch.add(x,x)
	  #乘法
	  x=torch.matmul(x,x)
	  
	  ```
- magic
	- ```python
	  #梯度计算
	  x=torch.tensor(3.0,requires_grad=True)#将变量标记为做梯度
	  y=x*x
	  y.backward()#反向演化
	  print(x.grad)# dy/dx保存在x.grad中
	  x.grad.zero_()#复用前清零
	  z=x*x*x
	  z.backward()
	  print(z.grad)
	  
	  #基本优化程序
	  #声明优化参数
	  w=torch.ones([1,1],requires_grad=True)#将变量标记为做梯度
	  b=torch.ones([1,1],requires_grad=True)#将变量标记为做梯度
	  #我猜：凡是被标记的变量，在他们进入函数中都会被跟踪，他们数据结构
	  #内部不仅保存有数值，还有他们进入函数后如何被操作的符号信息
	  #这些符号信息会被用来做梯度
	  #构建模型
	  def model(x):
	    return torch.matmul(x,w)+b
	  model(torch.tensor([1.0]))
	  #返回 tensor([[2.0]],grad_fn=<AddBackWad0>) 可见返回并不是单纯
	  #的一个数值，而是包含数值和符号信息的结构
	  
	  #设置优化器
	  optimizer=torch.optim.SGD([w,b],lr=learning_rate)
	  #告诉torch 它记录的torch变量中w,b需要跟踪优化
	  
	  inputs=torch.from_numpy(x_train)
	  targets=torch.from_numpy(y_train)
	  #inputs,targets虽然也是torch array,但是不需要被跟踪符号信息
	  outputs=model(inputs)
	  loss=mes(outputs,targets)
	  #这里loss除了保存模型计算出的数值，还保存了w,b的符号信息用于优化
	  optimizer.zero_grad() #数据清零
	  loss.backward() #根据当前input值以及符号信息计算梯度
	  #可以看出loss隐含继承了一个method，叫做backward(),这是从它的函数参数
	  #那里继承的
	  optimizer.step()#由于已经指明了优化变量，可以直接优化一步
	  
	  ```