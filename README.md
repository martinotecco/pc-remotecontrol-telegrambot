credits to [Tostapunk](https://github.com/Tostapunk) <br />
## How to install
<sup>**0.** first of all, be sure to navigate as a guest or in incognito mode, so close this page if you're navigating in the default mode and delete the browser history <br />
**1.** download the project from the [Releases section](https://www.github.com/martinotecco/pc-remotecontrol-telegrambot/releases) and unzip it in the Downloads folder<br />
<sup>(when unzipped, make sure to have the "pc-remotecontrol-telegrambot" folder containing directly the files, not another folder inside with the same name containing the files)</sup> <br />
**2.** open "python-3.11.3-amd64.exe" to install Python 3.11.3, select *Customize installation* to enable all the features <br />
<sup>(if you can only choose between *Modify*, *Repair* and *Uninstall*, choose *Modify* and enable all the features)</sup> <br />
**3.** open "VC_redist.x64.exe" to install Microsoft Visual C++ 14 and make sure to decline the reboot request at the end but, if it's already installed, close it <br />
**4.** open "vs_BuildTools.exe" to install Microsoft Visual Studio Build Tools 2022, you'll have to choose *Desktop development with C++* after <br />
<sup>(if it loads up automatically, first update all the installations, then, when you can see a message saying: 'All installations are up to date.', click on the *Modify* button and enable *Desktop Development with C++*)</sup> <br />
**5.** open "gpedit_enable.exe" to install Microsoft Local Security Policy and wait until the installation is complete, it will ask you to press any key at the end <br />
    <sup>(if prompted to a red alert window don't worry because it's safe, just click *More info*, then *Run anyway* and confirm by clicking *Yes*)</sup> <br />
**6.** search for secpol in the search bar, and click on *Local Security Policy* to open it <br />
    on the left side of the window click on the small arrow next to *Local Policies*, then click on *Security Options* <br />
    on the right side of the window find *Network access: Do not allow storage of passwords and credentials for network authentication* and make sure is disabled <br />
    <sup>(it should be already disabled but if it's enabled instead, click on it and choose *Disabled*, click on *Apply*, then *OK*)</sup> <br />
    find *Accounts: Limit local account use of blank passwords to console logon only*, click on it and choose *Disabled*, click on *Apply*, then *OK* <br />
    close the Local Security Policy window<br />
**7.** search for powershell in the search bar, right click on *Windows PowerShell* and select *Run as administrator*, then click *Yes* to confirm<br />
   when the console is open and ready, execute the following ten commands one at a time: <br />
   <sup>(remember to wait for it to be ready before typing each command)</sup> <br />
      `pip install --upgrade setuptools` <br />
      `python -m pip install --upgrade pip` <br />
      `pip install psutil` <br />
      `python -m pip install -r "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\requirements.txt"` <br />
      `Copy-Item -Path "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\bot" -Destination "C:\Windows\System32" -recurse -Force` <br />
      `attrib +s +h "C:\Windows\System32\bot"` <br />
      `Copy-Item -Path "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\batches" -Destination "C:\Windows\System32" -recurse -Force` <br />
      `attrib +s +h "C:\Windows\System32\batches"` <br />
      `batches\hide.bat` <br />
      `Set-ExecutionPolicy RemoteSigned -Force` <br />
   let the console opened, you don't have finished yet <br />
**8.** search for env in the search bar and click on *Edit the system environment variables* to open it <br />
    at the bottom of the window click on *Environment Variables...*, under the *System variables* section select the *Path* entry from the list and click *Edit...* <br />
    if you see two entries ending in *Python311\Scripts\\* and *Python311\\*, you can skip this step and close the environment variables editor <br />
    if you don't see those entries you have to add them, so in the console execute the following three commands: <br />
    <sup>(remember to wait for it to be ready before typing each command)</sup> <br />
    `.\"$env:userprofile\Downloads\pc-remotecontrol-telegrambot\path.py" |clip` <br />
    `Remove-Item "$env:userprofile\Downloads\pc-remotecontrol-telegrambot" -recurse -Force` <br />
    `Remove-Item "$env:userprofile\Downloads\pc-remotecontrol-telegrambot.zip" -recurse -Force` <br />
    let the console opened, go back to the list of entries and click on *New*, then press the Ctrl+V keybind to paste your Python path and press the Enter key <br />
    re-do the last step to add another entry to the list but, after pasting the path, add *Scripts\\* and then press the *Enter* key <br />
    click *OK* to confirm, then again and again for the third time, the environment variables editor should has closed <br />
**9.** if you don't have Telegram already installed on your phone, install it and create your account <br />
    go to [t.me/BotFather](https://t.me/BotFather) and in the chat press *START*, it'll reply with a list of commands; press on the */newbot* command and follow its replies <br />
    make sure to have your bot successfully created <br />
    <sup>(BotFather should has sent you a message with a t.me link to your bot and a token)</sup> <br />
    press on the token to copy it automatically <br />
    <sup>(if the computer doesn't sync your phone clipboard, to copy it easily send the token via email to a fake email account created with [temp-mail](https://temp-mail.org) → Ctrl+click to open the website in a new tab)</sup> <br />
**10.** in the console paste the following portion of a command, then add the BotFather token you've just copied and execute the command: <br />
    `py bot\bot_setup.py --token` <br />
    <sup>(it should look like this: ⠀ *py bot\bot_setup.py --token 3318732989:5p6mRpVuySvjGWFQea3FLHH872pF99HXF8N*)</sup> <br />
    now execute the following command to start the bot for the first time and then wait about 5/10 seconds before closing the console: <br />
    `py bot\bot_setup.py --start` <br />
    now you can close the console <br />
**11.** first, if you don't have a Telegram username, you have to create your username through your Telegram profile settings <br />
    press *START* in the chat of your newly created bot <br />
    <sup>(you can access your bot by pressing on the t.me link BotFather has sent you before; after pressing *START*, it should reply to you with: 'this is pc-remotecontrol-telegrambot!...' and 'the keyboard is up')</sup> <br />
    if a list of commands pops up you have to ignor it, there's another step you have to do before you can use those commands <br />
**12.** open again the console in administrator mode, paste the following portion of a command, then add your Telegram username and execute the command: <br />
    `py bot\bot_setup.py --admin_add` <br />
    <sup>(it should look like this: ⠀ *py bot\bot_setup.py --admin_add @username*)</sup> <br />
    now execute the following three commands and, after the last one, wait about 5/10 seconds before closing the console: <br />
    <sup>(remember to wait for it to be ready before typing each command)</sup> <br />
    `py bot\bot_setup.py --output_hide` <br />
    `py bot\bot_setup.py --startup_disable` <br />
    `py bot\bot_setup.py --start` <br />
    now you have to close the console <br />
**13.** search for task scheduler in the search bar and click on *Task Scheduler* to open it <br />
    <sup>(if you can't find it, search for task only instead)</sup> <br />
    in the top left corner click on *Action*, then choose *Create Task...* <br />
    in the *General* tab insert the name of the task, use "bot_restart.ps1" if you want, since it's the name of the script the task will run based on the schedule <br />
    select *Run whether user is logged on or not* and be sure to enable *Do not store password* and *Run with highest privileges* <br />
    go to the *Triggers* tab and click on *New...*, at the top, next to *Begin the task:*, should be already selected *On a schedule* <br />
    select *Daily*, then set the midnight, 00:00:00, of the current day as the date next to *Start:*, so remember that 00:00:00 is refered to the day after <br />
    <sup>(for example, if you're reading this on March 9th, set March 10th as the day and 00:00:00 as the time: the schedule will start at midnight)</sup> <br />
    next to *Recur every:* type *1* as the days count, then select *Repeat task every:* and set it to *5 minutes*, next to *for a duration of:* choose *Indefinitely* <br />
    be sure to disable the *Delay task for up to:* and *Expire:* features <br />
    select *Stop task if it runs longer than:* and set it to *30 minutes*, of course select *Enabled*, then click *OK* to confirm <br />
    re-do these last steps to create another trigger but, instead of *On a schedule*, in the new one you should choose *At startup* <br />
    set the other options equal to those of the previous trigger, except for the *for a duration of:* one, there you have to set *1 day* <br />
    go to the *Actions* tab and click on *New...*, at the top, next to *Action:*, should be already selected *Start a program* <br />
    in *Program/script:* paste *C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe*, in *Add arguments:* paste *C:\Windows\System32\bot\bot_restart.ps1* <br />
    leave the *Start in:* field blank and click *OK* to confirm <br />
    go to the *Conditions* tab and make sure to disable all the features <br />
    go to the *Settings* tab, then select *Allow task to be run on demand* and *Run task as soon as possible after a scheduled start is missed* <br />
    enable *If the task fails, restart every:* and set it to *1 minute*, then set *60* as the times it will attempt to restart <br />
    disable *Stop the task if it runs longer than:* and *If the task is not scheduled to run again, delete it after:* <br />
    enable *If the running task does not end when requested, force it to stop* <br />
    under *If the task is already running, then the following rule applies:* choose *Run a new instance in parallel*, then click *OK* to confirm <br />
    close the Task Scheduler window<br />
**14.** close the File Explorer window if it's still opened<br />
    press the Win+V keybind to open the clipboard, a small window should has appeared but, if you see a *Turn on* button, just close it, otherwise click *Clear all* <br />
    remember to close the web browser when you'll finish reading <br />
⠀ <br />
Done! You've set up the remote controller successfully. <br />
You can now use the commands in the chat of your Telegram bot to remote control the computer. <br />
Actually there are no bugs in the code, but maybe a few bugs haven't come up when testing. <br />
However, since the midnight of the day you've set it up, it should be always restarted automatically every 5 minutes, so if it crashes just wait a little. <br />
Please note that by executing the `batches\hide.bat` command, the shortcuts of those required programs installed at the beginning have been hidden <br />
and won't be listed when searching through the Start Menu. To unhide them, open the console in administrator mode and execute the following command: <br />
      `batches\unhide.bat`</sup> <br />
## Available commands
| Command | Description | Parameters |
| --- | --------- | --- |
| `/shutdown` | shutdown the computer | `_t <minutes>` <sub>e.g.: /shutdown_t 2 (not a mandatory parameter)</sub> |
| `/reboot` | reboot the computer | `_t <minutes>` <sub>e.g.: /reboot_t 2 (not a mandatory parameter)</sub> |
| `/cancel` | abort the shutdown or reboot |  |
| `/logout` | logout from the current account | `_t <minutes>` <sub>e.g.: /logout_t 2 (not a mandatory parameter)</sub> |
| `/lock` | lock down the computer |  |
| `/check` | check the computer status |  |
| `/keyboard`, `/kb` | show the commands in chat |  |
