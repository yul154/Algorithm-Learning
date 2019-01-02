# Pylab
> `import pylab as plt`
* plot two list:`plt.plot(list1,list2)`: list1 is x axis,list2 is y axis,Each execution of `plt.plot` will overlap in same window,
*`plt.figure`:Create a new display(window) with that name if one doesn't already exist, if exist, reopen the window 
* `plt.x_axis lab('labname')`: put lab in x axis
* `plt.title('title_name')`: put title on th graph
* `plt.clf`:clears the entire current figure with all its axes, but leaves the window opened
* `plt.close()`: close current window
* `plt.ylmi(limit number)`: set a limit number on y axis
* `plt.plot(....,lab='labname')`, `plt.legend(loc='location')`: put a legend to label different line
* Control detail on graph
  1. Line width: `plt.plot(.....,linewidth=float number)`
  2. Color and style: `plt.plot(...,'color+style'，label=)`
    * single dash: line, two dash: dash,o:circlr,^:triangle
  3. `plt.subplot(number of row+number of cols+number of location)`: setting limit number in order to compare
  4. Changing scales:'plt.yscale('scale_styple')'
