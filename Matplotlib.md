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
