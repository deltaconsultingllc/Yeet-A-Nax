# Yeet-A-Nax

A privately distributed Windows based YAF Roblox automation script for enchanting.  The script requires a dedicated PC but expect updates to expand on enchanting with other automation using multiple Roblox windows that can be devoted to hatching, star gazing, and throwing for example.  

![Yeet-A-Nax](https://i.imgur.com/Ch6Vx8j.png)
## Features

- Enchants a pet until the desired enchant is obtained
- Runs as an AutoHotKey V2 script on Windows
- Provides sound alert when enchant is completed
- Optionally can be enhanced using a execution environment which provides real-time visual feedback:
    - Visual output of time elapsed, roll count, and each enchant rolled
    - Outputs actual odds for obtained Enchants
    - Tracks star currency spent
    - Reports the total time spent for the enchant
- Supports minimized (800x600) or maximized window format at all desktop resolutions
- Recovers from accidental multi-tasking issues (experimental)
- Allows player to choose to accept rare enchants (Mimic, Secret Agent) when performing common enchants so that rare enchants are not missed.



## Installation

1. Download and install [Roblox Windows App](https://www.roblox.com/download/client?os=win)
2. Download and install [AutoHotKey V2](https://www.autohotkey.com/download/ahk-v2.exe)
3. Download, install, accept defaults, and run [Microsoft Visual Studio Code](https://code.visualstudio.com/Download)
4. In VSCode, Press `Ctrl+p` and type/paste `ext install mark-wiemer.vscode-autohotkey-plus-plus` then press `Enter` to install extension that handles `.ahk` files. 
5. Download the current Yeet-A-Nax.zip file here in discord.  Unzip all contents to any windows directory of your choice.
    
## How To Use

1. Have at least one instance of Roblox running (can be launched from Family Manager)

2. Move player to enchant station, select the pet you wish to enchant, and click the Purple Enchant button.

![Enchant Screen](https://i.imgur.com/574jagf.png)

3. In VSCode, use File\Open to open the Yeet-A-Nax.ahk file.

4. Press `Ctrl+Shift+Y` so that the DEBUG CONSOLE is shown.  Adjust the windowpane as needed (it will be blank to start)

5. Press `Ctrl+Alt+F9` to run the script.

6. Choose your desired enchant and check the below boxes if you want to keep the rare enchants should you land on one before the desired.  Click OK.

![Enchant Selection](https://i.imgur.com/oB6nQ3V.png)

7. A dialog box will prompt you that the next step is to select the roblox window.  Press OK.

8. Click anywhere on the instance of Roblox that is ready for enchanting.

9. Sit back and watch the DEBUG CONSOLE for status or wait until the "Found" sound plays.  I the example below, I selected Star Gazer and this is what you should see in the DEBUG CONSOLE:

![DEBUG CONSOLE](https://i.imgur.com/JyA4PLr.png)

10. To continue enchanting, select your next pet and click the Purple Enchant button.

11. Repeat starting at step 5.


## Stopping The Script
- `F7` will pause the Script

- `F10` will exit the Script

- If the script is running in VSCode `Shift+F5` will stop the script
## Settings

![Settings](https://i.imgur.com/NACth2s.png)

At the top of the .ahk file, there are a few settings that can be used.  Each will be explained below:

**Verbose Logging** - false by default.  If you are having a problem and can't determine the cause, you should change false to true and re-run.  Providing the debug console output in discord could be of use to help identify the problem.

**Enchant Wait Delay** - default is 200 milliseconds.  If your PC is slow and you notice that after the script clicks the enchant button that no roll occurs after 5 seconds, you may want to increase this value to compensate.  

**Run Maximized** - default is false so the Roblox window will run at 800x600 resolution.  Setting this to true maximizes Roblox to full screen.
## Recommended Roblox Settings
- Fullscreen should be turned Off
- Graphics Mode should be manual and Graphics Quality should be set to lowest value (it may work fine at higher values but untested)
## Roadmap

- Output a text log file of all enchants in comma delimited format that can be used with Excel or Google Sheets.  This will allow you to keep track of real-world odds so that you know generally the minimum, maximum, and average metrics for all enchant types.  Time expectations, Star Currency Cost, and Odds.

- Build support to manage more than one enchant at a given time (more instances of Roblox) so that more than one enchant is progressing at the same time on the same PC.

- Add capability to manage other Roblox instances performing hatching, star gazing, and throwing while keeping all windows active

## FAQ

#### Can I run other Roblox instances in the background (i.e. alts) to do other activities?

Short answer - currently, no.  Currently, the script forces the window to be in focus so that it can "see" the text\colors and to move the system mouse to click.  If you ran other instances, you would not be able to switch between seemlessly and likely they would time out due to inactivity.  In the roadmap section, part of the plan is to make this script multi-window aware and then task switch between multiple Roblox instances that can be pre-configured to do other things such as hatch, star gaze, and throw.

#### Will this run on mac or a tablet?

Mac maybe, but I haven't tested.  You would need to install something like "Parallels" so you have a windows instance within the mac environment.  Tablets are a no go.  Theoretically possible on android tablet but I'm not familiar enough with Android development to do it.

#### Will I get banned?  Is this against TOS?

It is unlikely that this can be detected because the Roblox window is manipulated through the same exact means...mouse clicks.  There are "hacking environments" out there that can exploit the game by injecting actions into the running code.  This is NOT what this script does and I would avoid those exploit engines as those are very detectable\bannable.  As far as TOS, I'm not aware of it but what happens in fight club, stays in fight club.

### I'm doing everything it says, but nothing happens in the debug window.  What could it be?

One problem I have seen is that Virus programs, such as Windows Defender, might think scripts are evil.  Either disable them or make sure AHK is whitelisted.

### Ctrl-Alt-F9 doesn't seem to run the script.  What gives? 

It's probably a hotkey conflict.  You can also run it by using a button.  See the image below and try clicking the button surrounded by the red rectangle:

![ALT RUN MODE](https://i.imgur.com/7fWc1Hi.png)

## Known Issues

- The script attempts to keep the Roblox window in focus during key events.  If you attempt to multitask, the program will likely handle and or recover fine.  However, I have seen instances where I pushed the limits and the script will fail with an "Unknown Color" error and a Raid Siren sound alert.  This issue is known and will hopefully be improved upon.
