## How to install
<sup>**1.** download the project from the [Releases section](https://www.github.com/martinotecco/pc-remotecontrol-telegrambot/releases) and unzip it in the Downloads folder<br />
<sup>(when unzipped, make sure to have the "pc-remotecontrol-telegrambot" folder containing directly the files, not another folder inside with the same name containing the files)</sup> <br />
**2.** open "python-3.11.1-amd64.exe" to install Python 3.11.1, make sure to select the option to add it to the PATH <br />
**3.** open "VC_redist.x64.exe" to install Microsoft Visual C++ 14 <br />
**4.** open "vs_BuildTools.exe" to install Microsoft Visual Studio Build Tools 2022, you'll have to choose *Desktop development with C++* after <br />
**5.** restart the computer <br />
**6.** search for powershell in the search bar, right click on *Windows PowerShell* and select *Run as administrator*, then click *Yes* <br />
   when the console is open and ready, execute the following two commands: <br />
   <sup>(remember to wait for it to be ready before typing each command)</sup> <br />
      `pip install --upgrade setuptools` <br />
      `pip install psutil` <br />
   now you can close the console <br />
**7.** restart the computer again <br />
**8.** open again the console in administrator mode and execute the following eight commands: <br />
   <sup>(remember to wait for it to be ready before typing each command)</sup> <br />
      `cd $env:userprofile\Downloads\pc-remotecontrol-telegrambot` <br />
      `python -m pip install -r requirements.txt` <br />
      `cd "C:\Windows\System32"` <br />
      `Copy-Item -Path "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\bot" -Destination "C:\Windows\System32" -recurse -Force` <br />
      `attrib +s +h "C:\Windows\System32\bot"` <br />
      `Copy-Item -Path "$env:userprofile\Downloads\pc-remotecontrol-telegrambot\batches" -Destination "C:\Windows\System32" -recurse -Force` <br />
      `attrib +s +h "C:\Windows\System32\batches"` <br />
      `batches\hide.bat` <br />
   now you can close the console <br />
**9.** restart the computer again <br />
**10.** if you don't have Telegram already installed on your phone, install it and create your account <br />
    go to t.me/BotFather and in the chat press *START*, it'll reply with a list of commands; press on */newbot* command and follow its replies <br />
    make sure to have your bot successfully created <br />
    <sup>(BotFather should has sent you a message with a t.me link to your bot and a token)</sup> <br />
    press on the token to copy it automatically <br />
    <sup>(if the computer doesn't sync your phone clipboard you won't have it copied on the computer clipboard, so, from your phone, send the token via email to the email account registered on the computer)</sup> <br />
**11.** open again the console in administrator mode and execute the following command: <br />
       `python bot\bot_setup.py` <br />
    a small window should has popped-up and you should see a blank field under the title *BotFather token* <br />
    paste your token in the blank field and click *Confirm*, then click *Start it!* <br />
    <sup>(the small window should has closed)</sup> <br />
    now you can close the console <br />
**12.** first, if you don't have a Telegram username, you have to create it through your Telegram profile settings <br />
    press *START* in the chat of your newly created bot <br />
    <sup>(you can access your bot by pressing on the t.me link BotFather has sent you before; after pressing *START*, it should reply to you with: 'Welcome to PC-Control bot...' and 'Keyboard is up')</sup> <br />
    if a list of commands pops-up you have to ignor it, there's another step you have to do before you can use those commands <br />
**13.** open again the console in administrator mode and execute the previous command <br />
    <sup>(press the up-arrow key on your keyboard and the command should appear in the console)</sup> <br />
    in the small window you have to click *Change user permissions*, then add your Telegram username without the @ symbol in the new blank field <br />
    close the Username window and click *Start it!* again <br />
    <sup>(your bot should has sent you a message showing: 'Bot up and running' and this is the message that informs you the remote controller is ready)</sup> <br />
    now you can close the console <br />
**14.** open again the console in administrator mode and execute the previous command <br />
    in the small window you have to click *Options*, *Console*, *Hide*, then click *Restart* and wait for it to re-opens <br />
    <sup>(by doing this the console will be invisible when executing commands from your Telegram bot)</sup> <br />
    click *Options* again, *Startup*, *Enable* <br />
    <sup>(by doing this, the remote controller will be available at every computer boot, it won't be necessary to start it again)</sup> <br />
    close the small window <br />
    before closing the console execute the following command: <br />
    `Remove-Item "$env:userprofile\Downloads\pc-remotecontrol-telegrambot" -recurse -Force` <br />
    <sup>(by executing this command the "pc-remotecontrol-telegrambot" folder has been deleted)</sup> <br />
    now you can close the console <br />
    delete the email you've sent to the email account registered on the computer, even from the trash, if you've copied the token by doing that <br />
    delete the browser research history <br />
**15.** restart the computer again</sup> <br />

<sup>DONE! You've set up the remote controller successfully, your bot will send you the 'Bot up and running' message at every computer boot. <br />
You can now use the commands in the chat of your Telegram bot to remote control the computer. <br />
Please note that by executing the `batches\hide.bat` command, those required programs installed at the beginning have been actually hidden <br />
and won't be listed when searching through the Start Menu. To unhide them, open the console in administrator mode and execute the following command: <br />
      `batches\unhide.bat`</sup> <br />
## Available commands
| Command | Description | Parameters |
| --- | --------- | --- |
| `/shutdown` | shutdown the computer | `_t + <minutes>` <sub>e.g.: /shutdown_t + 2</sub> |
| `/reboot` | reboot the computer | `_t + <minutes>` <sub>e.g.: /shutdown_t + 2</sub> |
| `/hibernate` | hibernate the computer | `_t + <minutes>` <sub>e.g.: /shutdown_t + 2</sub> |
| `/logout` | logout from the current account | `_t + <minutes>` <sub>e.g.: /shutdown_t + 2</sub> |
| `/lock` | lock the computer |  |
| `/cancel` | abort the shutdown or reboot |  |
| `/check` | check the computer status |  |
| `/launch` | launch a program | `<program>` <sub>e.g.: /launch notepad</sub> |
| `/task` | check if a process is running, <br /> if yes ask the user if he wants to kill it | `<exename>` <sub>e.g.: /task chrome</sub> |
| `/link` | open a webpage | `https://<domain>` <sub>e.g.: /link ht<span>tps://</span>google.com (don't use *w<span>ww.*)</sub> |
| `/memo` | show a memo on your computer | `<text>` <sub>e.g.: /memo hello, how are you?</sub> |
| `/screen` | take a screenshot and send it in the chat |  |
