credits to [Tostapunk](https://github.com/Tostapunk) <br />
## How to install
<sup>first of all, be sure to navigate as a guest or in incognito mode, so close this page if you're navigating in the default mode and delete the browser history <br />
**1.** download the project from the [Releases section](https://www.github.com/martinotecco/pc-remotecontrol-telegrambot/releases) and unzip it in the Downloads folder<br />
<sup>(when unzipped, make sure to have the "pc-remotecontrol-telegrambot" folder containing directly the files, not another folder inside with the same name containing the files)</sup> <br />
**2.** open "python-3.11.2-amd64.exe" to install Python 3.11.2, make sure to select the option to add it to the PATH <br />
**3.** open "VC_redist.x64.exe" to install Microsoft Visual C++ 14, make sure to decline the reboot request at the end <br />
**4.** open "vs_BuildTools.exe" to install Microsoft Visual Studio Build Tools 2022, you'll have to choose *Desktop development with C++* after <br />
**5.** search for powershell in the search bar, right click on *Windows PowerShell* and select *Run as administrator*, then click *Yes* <br />
   when the console is open and ready, execute the following eleven commands one at a time: <br />
   <sup>(remember to wait for it to be ready before typing each command)</sup> <br />
      `pip install --upgrade setuptools` <br />
      `pip install psutil` <br />
      `cd $env:userprofile\Downloads\pc-remotecontrol-telegrambot` <br />
      `python -m pip install -r requirements.txt` <br />
      `cd "C:\Windows\System32"` <br />
      `Copy-Item -Path "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\bot" -Destination "C:\Windows\System32" -recurse -Force` <br />
      `attrib +s +h "C:\Windows\System32\bot"` <br />
      `Copy-Item -Path "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\batches" -Destination "C:\Windows\System32" -recurse -Force` <br />
      `attrib +s +h "C:\Windows\System32\batches"` <br />
      `batches\hide.bat` <br />
      `Remove-Item "$env:userprofile\Downloads\pc-remotecontrol-telegrambot" -recurse -Force` <br />
   let the console opened, you don't have finished yet <br />
**6.** if you don't have Telegram already installed on your phone, install it and create your account <br />
    go to t.me/BotFather and in the chat press *START*, it'll reply with a list of commands; press on the */newbot* command and follow its replies <br />
    make sure to have your bot successfully created <br />
    <sup>(BotFather should has sent you a message with a t.me link to your bot and a token)</sup> <br />
    press on the token to copy it automatically <br />
    <sup>(if the computer doesn't sync your phone clipboard, to easily copy it send the token via email to a fake email account created with [temp-mail](https://temp-mail.org) ― Ctrl+click to open the website in a new tab)</sup> <br />
**7.** in the console execute the following command: <br />
       `py bot\bot_setup.py` <br />
    a small window should has popped-up and you should see a blank field under the title *BotFather token* <br />
    paste your token in the blank field and click *confirm*, then click *start it* and wait about 5/10 seconds<br />
    <sup>(the small window should has closed)</sup> <br />
    now you have to close the console <br />
**8.** first, if you don't have a Telegram username, you have to create your username through your Telegram profile settings <br />
    press *START* in the chat of your newly created bot <br />
    <sup>(you can access your bot by pressing on the t.me link BotFather has sent you before; after pressing *START*, it should reply to you with: 'this is pc-remotecontrol-telegrambot!...' and 'the keyboard is up')</sup> <br />
    if a list of commands pops-up you have to ignor it, there's another step you have to do before you can use those commands <br />
**9.** open again the console in administrator mode and execute the previous command <br />
    <sup>(press the up-arrow key on the keyboard and the command should appear in the console)</sup> <br />
    in the small window you have to click *change user permissions*, then insert your Telegram username without the @ symbol and click *add permissions* <br />
    close the username window, then click *start it* again and wait about 5/10 seconds<br />
    now you have to close the console <br />
**10.** open again the console in administrator mode and execute the previous command <br />
    in the small window you have to click *options*, *console*, *hide*, then click *restart* and wait for it to re-opens <br />
    <sup>(by doing this, the console will be invisible when executing commands from your Telegram bot)</sup> <br />
    click *start it* again and wait about 5/10 seconds<br />
    now you have to close the console <br />
**11.** search for task scheduler in the search bar and click on *Task Scheduler* to open it <br />
    in the top left corner click on *Action*, then choose *Create Task...* <br />
    in the *General* tab insert the name of the task, use "bot_restart.ps1" if you want, since it's the name of the script the task will run based on the schedule <br />
    choose *Run whether user is logged on or not* and be sure to enable *Do not store password.* and *Run with highest privileges* <br />
    go to the *Triggers* tab and click on *New...*, at the top, next to *Begin the task:*, should be already selected *On a schedule* <br />
    select *Daily*, then set the midnight, 00:00:00, of the current day as the date next to *Start:*, so remember that 00:00:00 is refered to the day after
⠀ <br />
Done! You've set up the remote controller successfully. <br />
You can now use the commands in the chat of your Telegram bot to remote control the computer. <br />
Please note that by executing the `batches\hide.bat` command, shortcuts of those required programs installed at the beginning have been actually hidden <br />
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
| `/task` | check if a program is running, <br /> if yes ask in chat if have to kill it | `<exename>` <sub>e.g.: /task chrome</sub> |
| `/link` | open a website | `https://<domain>` <sub>e.g.: /link ht<span>tps://</span>google.com (don't use *w<span>ww.*)</sub> |
| `/check` | check the computer status |  |
| `/keyboard`, `/kb` | show the commands in chat |  |
