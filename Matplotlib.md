Matplotlib is a low level graph plotting library in python that serves as a visualization utility. 
Matplotlib was created by John D. Hunter. 
Matplotlib is open source and we can use it freely.
Matplotlib is mostly written in python, a few segments are written in C, Objective-C and Javascript for Platform compatibility.
<hr>
📍Pyplot:

Most of the Matplotlib utilities lies under the pyplot submodule, and are usually imported under the plt alias:
```python
import matplotlib.pyplot as plt
```
Now the Pyplot package can be referred to as `plt`.
<hr>

📍Plotting x and y points:

✔️The `plot()` function is used to draw points (markers) in a diagram.

✔️By default, the `plot()` function draws a line from point to point.

✔️The function takes parameters for specifying points in the diagram.

✔️Parameter 1 is an array containing the points on the x-axis.

✔️Parameter 2 is an array containing the points on the y-axis.

If we need to plot a line from (1, 3) to (8, 10), we have to pass two arrays [1, 8] and [3, 10] to the plot function:
```python
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints)
plt.show()
```
❗The x-axis is the horizontal axis.

❗The y-axis is the vertical axis.
<hr>

📍Plotting Without Line:

To plot only the markers, you can use shortcut string notation parameter 'o', which means 'rings':
```python
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints, 'o')
plt.show()
```
<hr>

📍Multiple Points:

✔️You can plot as many points as you like, just make sure you have the same number of points in both axis.

Draw a line in a diagram from position (1, 3) to (2, 8) then to (6, 1) and finally to position (8, 10):
```python
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 2, 6, 8])
ypoints = np.array([3, 8, 1, 10])

plt.plot(xpoints, ypoints)
plt.show()
```
<hr>

📍Default X-Points:

✔️If we do not specify the points on the x-axis, they will get the default values 0, 1, 2, 3 etc., depending on the length of the y-points.

Plotting without x-points:
```python
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10, 5, 7])
#xpoint --> 0, 1, 2, 3, 4, 5

plt.plot(ypoints)
plt.show()

#(0,3) (1,8) (2,1) (3, 10) (4, 5) (5, 7)
```
<hr>

📍Markers:

✔️You can use the keyword argument `marker` to emphasize each point with a specified marker
```python
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker = 'o')
plt.show()
```
Markers:

- 'o'	Circle	
- '*'	Star	
- '.'	Point	
- ','	Pixel	
- 'x'	X	
- 'X'	X (filled)	
- '+'	Plus	
- 'P'	Plus (filled)	
- 's'	Square	
- 'D'	Diamond	
- 'd'	Diamond (thin)	
- 'p'	Pentagon	
- 'H'	Hexagon	
- 'h'	Hexagon	
- 'v'	Triangle Down	
- '^'	Triangle Up	
- '<'	Triangle Left	
- '>'	Triangle Right	
- '1'	Tri Down	
- '2'	Tri Up	
- '3'	Tri Left	
- '4'	Tri Right	
- '|'	Vline	
- '_'	Hline

<hr>

✔️Format Strings - `fmt`

You can also use the shortcut string notation parameter to specify the marker.

This parameter is also called `fmt`, and is written with this syntax:

`marker|line|color`

*If you leave out the line value in the fmt parameter, no line will be plotted.

```python
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, 'o:r')
#red circle points
plt.show()
```
Lines:

- '-'	Solid line
- ':'	Dotted line
- '--'	Dashed line
- '-.'	Dashed/dotted line

<hr>

📍Multiple Lines:

You can plot as many lines as you like by simply adding more `plt.plot()` functions:

```python
import matplotlib.pyplot as plt
import numpy as np

y1 = np.array([3, 8, 1, 10])
#x1 = [0, 1, 2, 3]
y2 = np.array([6, 2, 7, 11])
#x2 = [0, 1, 2, 3]

plt.plot(y1)
plt.plot(y2)

plt.show()
```
<hr>

📍Labels for a Plot:

✔️With Pyplot, you can use the `xlabel()` and `ylabel()` functions to set a label for the x- and y-axis.
```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([1, 2, 6, 8])
y = np.array([3, 8, 1, 10])

plt.plot(x, y)

plt.xlabel("LabelX")
plt.ylabel("LabelY")

plt.show()
```
<hr>

📍Position the Title:

✔️You can use the `loc` parameter in `title()` to position the title.

✔️Legal values are: 'left', 'right', and 'center'. Default value is 'center'.

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([1, 2, 6, 8])
y = np.array([3, 8, 1, 10])

plt.plot(x, y)

plt.title('Title', loc='left')
plt.xlabel("LabelX")
plt.ylabel("LabelY")

plt.show()
```
<hr>

📍Add Grid Lines to a Plot:

✔️With Pyplot, you can use the `grid()` function to add grid lines to the plot.

Add grid lines to the plot:
```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([1, 2, 6, 8])
y = np.array([3, 8, 1, 10])

plt.plot(x, y)

plt.grid()

plt.show()
```
✔️You can use the axis parameter in the grid() function to specify which grid lines to display.

✔️Legal values are: 'x', 'y', and 'both'. Default value is 'both'.

```python
plt.grid(axis = 'x')
#or
plt.grid(axis = 'y')
```
<hr>

📍Matplotlib Subplot:

✔️Display Multiple Plots:

With the `subplot()` function you can draw multiple plots in one figure:
```python
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(1, 2, 1)
plt.plot(x,y)

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(1, 2, 2)
plt.plot(x,y)

plt.show()
```
✔️The `subplot()` function:
- Takes three arguments that describes the layout of the figure.
- The layout is organized in rows and columns, which are represented by the first and second argument.
- The third argument represents the index of the current plot.

```python
plt.subplot(1, 2, 1)
#the figure has 1 row, 2 columns, and this plot is the first plot.

plt.subplot(1, 2, 2)
#the figure has 1 row, 2 columns, and this plot is the second plot.
```

✔️Title - You can add a title to each plot with the `title()` function (to each plot)

✔️Super Title - You can add a title to the entire figure with the `suptitle()` function(for the entire figure)
<hr>

📍Matplotlib Scatter:

✔️With Pyplot, you can use the `scatter()` function to draw a scatter plot.

✔️The `scatter()` function plots one dot for each observation. It needs two arrays of the same length, one for the values of the x-axis, and one for values on the y-axis:
```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([1, 2, 6, 8])
y = np.array([3, 8, 1, 10])

plt.scatter(x, y)
plt.show()
```
✔️You can compare plots by creating two plots (they will be in different colors)

✔️You can set your own color for each scatter plot with the `color` or the `c` argument.
<hr>

📍ColorMap:

✔️The Matplotlib module has a number of available colormaps.

✔️A colormap is like a list of colors, where each color has a value that ranges from 0 to 100.

✔️You can specify the colormap with the keyword argument `cmap` with the value of the colormap, in this case `'viridis'` which is one of the built-in colormaps available in Matplotlib.

✔️In addition you have to create an array with values (from 0 to 100), one value for each point in the scatter plot

✔️You can include the colormap in the drawing by including the `plt.colorbar()` statement:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
colors = np.array([0, 10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 100])

plt.scatter(x, y, c=colors, cmap='viridis')

plt.colorbar()

plt.show()
```
<hr>

📍Size:

✔️You can change the size of the dots with the `s` argument.

✔️Just like colors, make sure the array for sizes has the same length as the arrays for the x- and y-axis:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
sizes = np.array([20,50,100,200,500,1000,60,90,10,300,600,800,75])

plt.scatter(x, y, s=sizes)

plt.show()
```
<hr>

📍Alpha:

✔️You can adjust the transparency of the dots with the `alpha` argument.

✔️Just like colors, make sure the array for sizes has the same length as the arrays for the x- and y-axis:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
sizes = np.array([20,50,100,200,500,1000,60,90,10,300,600,800,75])

plt.scatter(x, y, s=sizes, alpha=0.5)

plt.show()
```
<hr>

📍Matplotlib Bars:

✔️With Pyplot, you can use the `bar()` function to draw bar graphs(vertical):
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x,y)
plt.show()
```
✔️The `bar()` function takes arguments that describes the layout of the bars.

✔️The categories and their values represented by the first and second argument as arrays.

✔️If you want the bars to be displayed horizontally instead of vertically, use the `barh()` function:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.barh(x, y)
plt.show()
```
✔️Bar Width - The bar() takes the keyword argument width to set the width of the bars:
```python
plt.bar(x, y, width = 0.1)
```
*For horizontal bars, use height instead of width.

*The default value is 0.8

<hr>

📍Matplotlib Histograms:

✔️A histogram is a graph showing frequency distributions.

✔️It is a graph showing the number of observations within each given interval.

✔️In Matplotlib, we use the `hist()` function to create histograms.

✔️The `hist()` function will use an array of numbers to create a histogram, the array is sent into the function as an argument.

For simplicity we use NumPy to randomly generate an array with 250 values, where the values will concentrate around 170, and the standard deviation is 10. The `hist()` function will read the array and produce a histogram:
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.random.normal(170, 10, 250)

plt.hist(x)
plt.show() 
```
<hr>

📍Matplotlib Pie Charts:

✔️With Pyplot, you can use the `pie()` function to draw pie charts:
```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])

plt.pie(y)
plt.show() 
```
✔️By default the plotting of the first wedge starts from the x-axis and moves counterclockwise

✔️Labels - Add labels to the pie chart with the `labels` parameter. The `labels` parameter must be an array with one label for each wedge:
```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.show()
```
✔️Start Angle - As mentioned the default start angle is at the x-axis, but you can change the start angle by specifying a `startangle` parameter. The `startangle` parameter is defined with an angle in degrees, default angle is 0:

```python
plt.pie(y, labels = mylabels, startangle = 90)
```

✔️Explode - The `explode` parameter allows wedges to stand out. The `explode` parameter, if specified, and not `None`, must be an array with one value for each wedge. Each value represents how far from the center each wedge is displayed:
```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]
myexplode = [0.2, 0, 0, 0]

plt.pie(y, labels = mylabels, explode = myexplode)
plt.show() 
```
✔️Legend - To add a list of explanation for each wedge, use the `legend()` function. To add a header to the legend, add the `title` parameter to the `legend` function.
```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.legend(title = "Four Fruits:")
plt.show() 
```
