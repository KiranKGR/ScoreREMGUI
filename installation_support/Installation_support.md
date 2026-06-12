# Installation Guidance for Windows

## ScoreREM: A user friendly MATLAB-GUI for rapid eye movement (REM) sleep microstructure annotation and quantification

**Licence:** ScoreREM Copyright (C) 2024 Kiran K G Ravindran. Refer to the License.txt for more details.

For smooth installation, please perform the tasks below as an Administrator. The instructions are provided for Windows Operating system (OS) with comments on how to perform the same checks in Mac and Linux based OS. For use in any OS, user needs to ensure python 3.11.6 and the supporting packages are installed, Matlab 2023b is installed and the python 3.11.6 is the version used by Matlab 2023b. Note: The ScoreREM will operate normally even without the python but the automated scoring options will be unavailable. 

### MATLAB:

1. Install MATLAB 2023b. 
    - Toolbox required: Signal Processing Toolbox

2. Check if a compatible Python installation is already available by calling `pyenv` in the command window to know the Python version installed.

![pyenv](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/7e057645-35c8-44c0-ae85-b09f2938fab6)

3. If there are no supported python packages you will see

![PyEnv_no python](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/a86da352-8f33-4915-aba7-74fceab7262e)

If no supported Python installation is available, please follow the `Python` installation instructions below. 

Further documentation on supported Python installation can be found [here - Configure Your System to Use Python](https://uk.mathworks.com/help/matlab/matlab_external/install-supported-python-implementation.html).

### Python:

1. Download and install Python 3.11.6 from the following link: [Python-3.11.6-amd64.exe](https://www.python.org/ftp/python/3.11.6/python-3.11.6-amd64.exe). 
    - Choose "Add Python.exe to PATH" in the pop-up installer.

-In case of MacOS or Linux OS versions, please find and install Python 3.11.6 from [here](https://www.python.org/downloads/release/python-3116/)

-Installation instructions for Ubuntu can be found [here](https://www.geeksforgeeks.org/how-to-install-python-in-ubuntu/)

2. Open a command prompt by typing `PowerShell` into the search bar in the Start menu and then clicking on PowerShell.
    - In MacOS / in Ubuntu use `Terminal` to perform the same checks.

4. Check if the Python version is 3.11.6:
    ```PowerShell
    python --version
    ```

5. For MATLAB to identify Python, it needs to be on the top of the system PATH for MATLAB to use it. If the Python version is not 3.11.6, you can add it following the steps below:

- Step 1: Find the location of the exe file of Python311 (Usual location: `C:\Users\yourusername\AppData\Local\Programs\Python\Python311`).

![python](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/f15ce5ce-5235-42aa-83d3-ab4431d81f81)

Type `Python.exe` in the Windows search. Right-click on `Python.exe` and choose "Open file location." Copy the path to the folder (see image below). (Similar operations can performed in other OS's to get the path)

![copyfilepath](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/067edd7b-9fd8-4ee2-9136-ae5467d98e89)

- Step 2: Add the python path to system environments (Find instructions for MacOS, [here](https://mac.install.guide/python/path) and for Linux, [here](https://stackoverflow.com/questions/18247333/pythonpath-on-linux))
1. Type in "system env" and click on "edit system environment variables".

![system env](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/d8c467a4-4c79-4e47-883b-8dec749af6ab)

2. Click on the "Advanced" tab at the top.

3. At the bottom, click the button that says "Environment Variables".

![systemproperties](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/5a23d94c-ce46-44f0-abe5-b8583d431a29)

4. Now on the "User variables 'your user name'" box at the top of the window, click on "Path".
    - If you have chosen "Add Python to PATH" during installation, you will find `…\Python311` and `…\Python311\Scripts` there. Move them to the top and click OK.

![EditenvVar](https://github.com/KiranKGR/ScoreREMGUI/assets/94359263/90a7b364-e428-43de-8b34-1bab21b05091)
  
    - If they are not there, click "Edit". This should lead to another window where you want to click "New" and type in the commands:
        ```plaintext
        C:\Users\yourusername\AppData\Local\Programs\Python\Python311
        C:\Users\yourusername\AppData\Local\Programs\Python\Python311\Scripts
        ```

5. Restart the system.

6. Check if Python 3.11.6 is showing up as the Python version:
    ```PowerShell
    python --version
    ```

7. Now install the required packages: numpy, pandas, pytz, mne, yasa, [EDFlib](https://pypi.org/project/EDFlib-Python/)
    ```PowerShell
    python -m pip install --upgrade pip
    python -m pip install numpy pandas pytz mne yasa EDFlib
    ```
    
8. Once this is successful, please open MATLAB and check the Python environment using `pyenv`. It should show the version as 3.11.
    - If it's not showing up, please restart the computer, open MATLAB, and try again.

### After performing the installation and checks, the ScoreREM app can be installed by double clicking on the .mlappinstall file. (Note: When the app is started for the for the first time during a Matlab session, it checks the presence of python packages required which takes several minutes to perform. Further, Please check whether you PC has enough RAM space to perform the data import)

We have provided a [**standalone version of ScoreREM**](https://github.com/KiranKGR/ScoreREMGUI/tree/2ee7f8c4e502ad681c1b462a68c1353d61cdbf46/src/Standalone_App_for_redistribution) which works with the Matlab runtime.

## Common Issue: Windows in some cases names the EDFlib package in lower case making it invisible to Matlab. 
* In your python installation visible to Matlab, It will show up as edflib in your \\AppData\Local\Programs\Python\Python311\Lib\site-packages path (PACKAGE CONTENTS:  edfreader  edfwriter). You just have to capitalise EDF so that Matlab can find it.
* You will be able to path to the site-packages folder using pyenv in command window. 
* Once you modify the folder name. Please restart Windows and check if the package is visible to matlab using the following command in the Matlab command window: **py.importlib.import_module("EDFlib")**
