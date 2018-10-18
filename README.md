# tkmultikey
## Overview
A simple python library to allow multi-key combinations to be bound in python. It aims to do this in the most beginner-friendly way by overriding a tkinter widgets original bind function with a custom version to allow multiple keys to be specified as the condition for a function's execution.
## Installation
Installation of the library is incredibly simple using either command line or the browser.
##### Command-line:
- Download the library's source file using the following command **in the directory of your python program**.
```
git clone http://www.github.com/lorcajheeney/tkmultikey
```
##### Browser:
- Visit http://www.github.com/lorcajheeney/tkmultikey on your browser.
- Click the `clone or download` button.
- Click `download zip` and store the download **in the directory of your python program**.
- Extract the downloaded zip to the current directory.
## Use
The library is easily included in the any python program via the following import statement.
```python
import tkmultipy
```
There is only one public function within the library, `config`. Pass a `tkinter.Tk()` instance to it as its sole paramter to initalize the functionality of the library as shown below.
```python
import tkinter
import tkmultipy

window = tkinter.Tk()
tkmultipy.config(window)
```
**NOTE : Calling `config` on an instance will override that instance's bind and update methods, this may lead to undefined behaviour if those methods are not used correctly even if the use would be correct on the original functions.**
## Example
Shown below, is an example project which uses `tkmultipy` to  increase the size of the window when the space bar and right arrow key is pressed.
```python
import tkinter
import tkmultikey

WIDTH, HEIGHT = 640, 480

def increase_size():
    global WIDTH, HEIGHT
    WIDTH += 1
    HEIGHT += 1
    window.geometry("{}x{}".format(WIDTH,HEIGHT))

window = tkinter.Tk()
tkmultikey.config(window)

window.bind("<space>+<Right>",increase_size)
while True:
    window.update()
```

