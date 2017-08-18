# PythonInst
Helps installing Python 2.7 with ArcGIS and other scientific libaries (Numpy, Pandas, ...) on Windows 7. The problem is that if you want to use arcpy together with other scientific modules in Python, you must install these modules inside the Python version that ships with ArcGIS.


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

   ```>>> import numpy```

   ```>>> numpy.__version__```

   If the version is older than 1.6, then first try to upgrade:
   
   ```python -pip install --upgrade numpy```
   
   if that does not work, uninstall:
   
   ```python -pip uninstall numpy```
   
- If there is no numpy (''no module named numpy'') or to install from scratch: Click and download the newest precompiled wheel at http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy. Put the wheel in the installation folder and install it with (using the correct filename):

     ```python -pip install numpy-1.11.1+mkl-cp27-cp27m-win32.whl```

    make sure you select the correct Python folder (!).

- Test numpy with:

    ```>>> import numpy```
    
    ```>>> print numpy.__version__```
    
## 4 Install other required packages and Pandas

- In the same way as numpy above, install also http://www.lfd.uci.edu/~gohlke/pythonlibs/#python-dateutil, http://www.lfd.uci.edu/~gohlke/pythonlibs/#pytz, http://www.lfd.uci.edu/~gohlke/pythonlibs/#setuptools. (Check first whether packages are already present, as above).

- Optionally, you can also install http://www.lfd.uci.edu/~gohlke/pythonlibs/#matplotlib (to visualize plots), http://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy, and http://www.lfd.uci.edu/~gohlke/pythonlibs/#statsmodels.

- Then install *pandas* simply by

  ```python -pip install pandas```
    
  and test whether it works by:

  ```>>> import pandas```
   
    
## For other packages (Fiona, Shapely, GDAL,...):

First try to install package using:

   ```python -pip install yourpackage```
   
If that fails, try the package with the newest Gohlke wheel on http://www.lfd.uci.edu/~gohlke/pythonlibs/.



    
   
   
   


