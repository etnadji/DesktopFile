# Desktop File
## About
desktop-file is a tool to create desktop shortcuts for windows and linux.
## Installation
To install desktop-file you need [python](https://www.python.org/downloads/release) 3 or later with setuptools installed.<br/>
Then you can install it by cloning or downloading this repository and executing `python setup.py install`.
## Usage
### Python
You can use it in your python script like this:<br/>
```
>>> import desktop_file
>>> # get desktop and start menu folders
>>> desktop_file.getDesktopPath()
/home/PyRectangle/Desktop
>>> desktop_file.getMenuPath()
/home/PyRectangle/.local/share/applications`
>>> # create a xterm shortcut
>>> shortcut = desktop_file.Shortcut("/home/PyRectangle/Desktop", "XTerm", "/usr/bin/xterm")
>>> shortcut.setWorkingDirectory("/home/PyRectangle")
>>> shortcut.setComment("A desktop file to start xterm")
>>> # Only ".ico" files work on Windows
>>> shortcut.setIcon("/usr/share/pixmaps/mini.xterm_48x48.xpm")
>>> # Categories don't have any effects on Windows
>>> shortcut.setCategories("System;")
>>> shortcut.save()
```
You will find a working shortcut named "XTerm" in the folder "/home/PyRectangle/Desktop"


### Command
You can also use `python -m desktop_file` or `desktop-file` to create shortcuts like this:<br/>
```
desktop-file --exec xterm --workpath /home/PyRectangle --comment "A desktop file to start xterm" --icon /usr/share/pixmaps/mini.xterm_48x48.xpm --categories "System;" /home/PyRectangle/Desktop/XTerm.desktop
```
You will need to type ".lnk" instead of ".desktop" if you are on Windows.
