# obs-rec-rename
### OBS recording renamer, appends full screen window title to finished recordings and instant replays.

## Installation
The script, and to the best of my knowledge OBS, require Python 3.6. Alongside the Python install and correct settings for the Python scripts on OBS - [pywin32](https://pypi.org/project/pywin32/) and [psUtil](https://pypi.org/project/psutil/) are required. These can be installed via pip, but I faced issues with win32gui, so i installed that from the installer found [here](https://github.com/mhammond/pywin32/releases)
```
pip install pywin32
pip install psutil
```
Once Python is setup, the script can be placed in any directory.

## Usage
Once installed, the script "RecordingRenamer.py" can be pointed to within the OBS scripts function, and 4 options will need to be set:
- Output Directory: The folder OBS outputs the recordings to.
- Extension: The filetype OBS is outputting (not including the .)
- Time Interval: This is how often the renaming function of the script runs in seconds.
- Remove mkv's: Use this check box if you would like to remove the old mkv files left behind once the files have been successfully renamed.

The script will then run whenever a recording is finished, or an instant replay buffer is saved.

## Configuration
There is not much extra configuration for the script, but if you would like to ignore certain executables, and have them fall-back to the default "Desktop" title, or to override non full-screen windows and use thier title rather than the default "Desktop". These list of executables are maintained in the "FullscreeOveride.cfg" and "DesktopOverride.cfg"

## Details
The scrpt detects the title of the foreground window when ever the recording or instant replay is saved. If the window is the OBS window, it will label the recoding "Manual Recording". If the window is detected as fullscreen on the primary monitor, it will label the recording that windows title (unless the executable is in the "FullscreenOverride.cfg" list. If the window is not fullscreen, the recording will be lablled "Desktop", unless the executable appears in the "DesktopOverride.cfg" file. 
