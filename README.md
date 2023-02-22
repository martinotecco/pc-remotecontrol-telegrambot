credits to [Tostapunk](https://github.com/Tostapunk/) <br />
## How to install
<sup>**1.** download the project from the [Releases section](https://www.github.com/martinotecco/pc-remotecontrol-telegrambot/releases) and unzip it in the Downloads folder<br />
<sup>(when unzipped, make sure to have the "pc-remotecontrol-telegrambot" folder containing directly the files, not another folder inside with the same name containing the files)</sup> <br />
**2.** open "python-3.11.1-amd64.exe" to install Python 3.11.1, make sure to select the option to add it to the PATH <br />
**3.** open "VC_redist.x64.exe" to install Microsoft Visual C++ 14, make sure to decline the reboot request at the end <br />
**4.** open "vs_BuildTools.exe" to install Microsoft Visual Studio Build Tools 2022, you'll have to choose *Desktop development with C++* after <br />
**5.** search for powershell in the search bar, right click on *Windows PowerShell* and select *Run as administrator*, then click *Yes* <br />
   when the console is open and ready, execute the following ten commands: <br />
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
   let the console open, you don't have finished yet <br />
**6.** if you don't have Telegram already installed on your phone, install it and create your account <br />
    go to t.me/BotFather and in the chat press *START*, it'll reply with a list of commands; press on the */newbot* command and follow its replies <br />
    make sure to have your bot successfully created <br />
    <sup>(BotFather should has sent you a message with a t.me link to your bot and a token)</sup> <br />
    press on the token to copy it automatically <br />
    <sup>(if the computer doesn't sync your phone clipboard you won't have it copied on the computer clipboard, so, from your phone, send the token via email to the email account registered on the computer)</sup> <br />
**7.** in the console execute the following command: <br />
       `python bot\bot_setup.py` <br />
    a small window should has popped-up and you should see a blank field under the title *BotFather token* <br />
    paste your token in the blank field and click *confirm*, then click *start it* <br />
    <sup>(the small window should has closed)</sup> <br />
    now you have to close the console <br />
**8.** first, if you don't have a Telegram username, you have to create your username through your Telegram profile settings <br />
    press *START* in the chat of your newly created bot <br />
    <sup>(you can access your bot by pressing on the t.me link BotFather has sent you before; after pressing *START*, it should reply to you with: 'welcome to pc-remotecontrol-telegrambot...' and 'the keyboard is up')</sup> <br />
    if a list of commands pops-up you have to ignor it, there's another step you have to do before you can use those commands <br />
**9.** open again the console in administrator mode and execute the previous command <br />
    <sup>(press the up-arrow key on the keyboard and the command should appear in the console)</sup> <br />
    in the small window you have to click *change user permissions*, then insert your Telegram username without the @ symbol and click *add permissions* <br />
    close the username window and click *start it* again <br />
    now you have to close the console <br />
**10.** open again the console in administrator mode and execute the previous command <br />
    in the small window you have to click *options*, *console*, *hide*, then click *restart* and wait for it to re-opens <br />
    <sup>(by doing this, the console will be invisible when executing commands from your Telegram bot)</sup> <br />
    click *options* again, *startup*, *enable* <br />
    <sup>(by doing this, the remote controller will be available at every computer boot, it won't be necessary to start it again)</sup> <br />
    close the small window <br />
    in the console execute the following command: <br />
    `Remove-Item "$env:userprofile\Downloads\pc-remotecontrol-telegrambot" -recurse -Force` <br />
    <sup>(by executing this command, the "pc-remotecontrol-telegrambot" folder has been deleted)</sup> <br />
    click *start it* again <br />
    now you have to close the console <br />
    delete the email you've sent to the email account registered on the computer, even from the trash, if you've copied the token by doing that <br />
    delete the browser research history</sup> <br />
<sup>Done! You've set up the remote controller successfully. <br />
You can now use the commands in the chat of your Telegram bot to remote control the computer. <br />
Please note that by executing the `batches\hide.bat` command, shortcuts of those required programs installed at the beginning have been actually hidden <br />
and won't be listed when searching through the Start Menu. To unhide them, open the console in administrator mode and execute the following command: <br />
      `batches\unhide.bat`</sup> <br />
## Available commands
| Command | Description | Parameters |
| --- | --------- | --- |
| `/shutdown` | shutdown the computer | `_t <minutes>` <sub>e.g.: /shutdown_t 2 (not a mandatory parameter)</sub> |
| `/reboot` | reboot the computer | `_t <minutes>` <sub>e.g.: /reboot_t 2 (not a mandatory parameter)</sub> |
| `/hibernate` | hibernate the computer | `_t <minutes>` <sub>e.g.: /hibernate_t 2 (not a mandatory parameter)</sub> |
| `/logout` | logout from the current account | `_t <minutes>` <sub>e.g.: /logout_t 2 (not a mandatory parameter)</sub> |
| `/lock` | lock the computer |  |
| `/cancel` | abort the shutdown or reboot |  |
| `/check` | check the computer status |  |
| `/launch` | launch a program | `<program>` <sub>e.g.: /launch notepad (no matter uppercase or lowercase)</sub> |
| `/task` | check if a process is running, <br /> if yes ask in chat if have to kill it | `<exename>` <sub>e.g.: /task chrome</sub> |
| `/link` | open a website | `https://<domain>` <sub>e.g.: /link ht<span>tps://</span>google.com (don't use *w<span>ww.*)</sub> |
| `/memo` | show a memo | `<text>` <sub>e.g.: /memo Hello, how are you? (WARNING! the UI is visible)</sub> |
| `/screen` | take a screen and send it in chat |  |
| `/keyboard`, `/kb` | show the commands in chat |  |
