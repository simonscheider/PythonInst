# PythonInst
Helps installing Python 2.7 with ArcGIS and other scientific libaries (Numpy, Pandas, ...) on Windows 7


## 1 Localize and check your ArcGIS Python installation
You need to know where ArcGIS's Python installation is located, and make sure your command line tool knows it, too, by setting windows environment variables.

- Find the Python folder that ships with your ArcGIS installation. This is normally (for ArcMap 10.3):

    ```C:\Python27\ArcGIS10.3 ```

- Open  cmd.exe. Find the location of python as currently used in the *windows system environment* with: 

    ```python -c "import sys; print sys.executable"```

- In case python "is not recognized as an internal or external command", or in case python is recognized but the path that is dipsplayed does *not* correspond to your ArcGIS Python folder identified above: Set the right python version as an environment variable. To do so, open Control panel/System/Advanced System Settings/Environment Variable, and:     
    - Add ```C:\Python27\ArcGIS10.3``` to the end of the PATH system variable (but before any other python version)
    - Add ```C:\Python27\ArcGIS10.3``` to the end of the PYTHONPATH system variable (but before any other python version)
    - Test whether the correct python is recognized now in the cmd window. If yes, then you can start installation of Python modules.

- In cmd. exe, move to the installation directory for modules. This is where all python modules get installed:

   ```cd C:\Python27\ArcGIS10.3\Lib\site-packages```    

## 2 Pip installer
You need a python installer to make module installation easy.

- Is pip installed already? Try this in cmd.exe:

    ```python -m pip```    
    
    If this command is recognized, pip can be used rightaway. 
    
- Otherwise, it needs to be installed. For this purpose, download [get-pip.py](https://bootstrap.pypa.io/get-pip.py), being careful to save it as a .py file rather than .txt. you need to put *get-pip.py* into the installation directory. Then, run it from the command prompt:

   ```python get-pip.py```
   
   You possibly need ad administrator command prompt to do this. Follow [Start a Command Prompt](http://technet.microsoft.com/en-us/library/cc947813(v=ws.10).aspx) as an Administrator. 
   
   Once pip is installed, add its path (```C:\Python27\ArcGIS10.3\Scripts\pip.exe```) to the PATH environment variable to use it directly in the command prompt (see above). Test whether everything works  with ```python -m pip```.
 
## 3 Install/Update numpy
Numpy is crucial for all of scientific computing. Although it ships with ArcGIS (), it often needs to be updated to a newer version that can be used with e.g. Pandas. First check whether numpy is installed and which version:

- Check whether numpy is installed in cmd.exe by typing in:

   ```python``` 

   ```import numpy```

   ```numpy.__version__```

   If the version is older than 1.6, then first try to upgrade:
   
   ```python pip install --upgrade numpy```
   
   if that does not work, uninstall:
   
   ```python pip uninstall numpy```
   
- If there is no numpy or to intall anew: Click and download the newest precompiled wheel at http://www.lfd.uci.edu/~gohlke/pythonlibs/
    for example [http://pypi.python.org/packages/2.7/n/numpy/numpy-1.6.1.win32-py2.7.exe] (http://pypi.python.org/packages/2.7/n/numpy/numpy-1.6.1.win32-py2.7.exe). Run the installer, select the correct Python folder to install into, and follow the process to the end.
    

    
   
   
   


