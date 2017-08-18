# PythonInst
Helps installing Python 2.7 with ArcGIS and other scientific libaries on Windows 7


## 1 Localize and check your ArcGIS Python installation
You need to know where ArcGIS's Python installation is located, and make sure your command line tool knows it, too, by setting windows environment variables.

- Find the Python folder that ships with your ArcGIS installation. This is normally (for ArcMap 10.3):

    ```C:\Python27\ArcGIS10.3 ```

- Open  cmd.exe. Find the location of python as currently used in the *windows system environment* with: 

    ```python -c "import sys; print sys.executable"```

- In case python "is not recognized as an internal or external command", or in case python is recognized but the path that is dipsplayed does *not* correspond to your ArcGIS Python folder identified above: Set the right python version as an environment variable. To do so, open Control panel/System/Advanced System Settings/Environment Variable, and:     
    - Add ```C:\Python27\ArcGIS10.3``` to the end of the PATH system variable (but before any other python version)
    - Add ```C:\Python27\ArcGIS10.3``` to the end of the PYTHONPATH system variable (but before any other python version)
    - Test whether the correct python is recognized now in the cmd window.
- 
