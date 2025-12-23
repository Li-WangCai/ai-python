- ```python
  def plotfun(para):
    x=np.linespace(0,1,100)
    plt.plot(x,np.sin(x*para))
  widgets.interact(plotfun,para=widgets.IntSlider(min=0,max=10,step=1,value=2))
  ```