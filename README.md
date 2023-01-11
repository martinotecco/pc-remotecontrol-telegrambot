INSTALLATION

1. open "python-3.11.1-amd64.exe" to install Python 3.11.1, make sure to select the option to add it to the PATH
2. open "VC_redist.x64.exe" to install Microsoft Visual C++ 14
3. open "vs_BuildTools.exe" to install Microsoft Visual Studio Build Tools 2022, you'll have to choose 'Desktop development with C++' after
4. restart the computer
5. search for 'PowerShell' in the search bar, right click on it and select 'Run as administrator', then click 'Yes'
   when the console is open and ready, execute the following two commands (remember to wait for it to be ready after typing each command):
      pip install --upgrade setuptools
      pip install psutil
   now you can close the console
6. restart the computer again
7. open again the console and execute the following four commands, as described in the first and second lines of step 5:
      cd $env:userprofile\Downloads\pc-remotecontrol-telegrambot
      python -m pip install -r requirements.txt
      Copy-Item -Path $env:userprofile\Downloads\pc-remotecontrol-telegrambot\bot -Destination "C:\Windows\System32" -recurse -Force
      attrib +h "C:\Windows\System32\bot" /s /d
   now you can close the console
9. restart the computer again
10. if you don't have Telegram already installed on your phone, install it and create your account
    go to t.me/BotFather and in the chat press 'START', it'll reply with a list of commands; press on '/newbot' command and follow its replies
    make sure to have your bot successfully created (BotFather should has sent you a message with a t.me link to your bot and a token)
    press on the token to copy it automatically (if the computer doesn't sync the phone clipboard you won't have it copied on the computer clipboard, so, from your phone, send an email to the email account registered on the computer including the token in the text: you'll open it on the computer and will copy the token, then remember to delete that email, even from the trash, and delete also the browser research history!)
11. open again the console and execute the following command:
       python bot\bot_setup.py
    a small window called 'Setup' (actually 'Set...') should has popped-up and you should see a blank field under the title 'BotFather token': this small window it's the setup of the remote controller
    paste your token in the blank field and click 'Confirm', then click 'Start it!' (the small window should has closed)
    now you can close the console
12. first, if you don't have a Telegram username (@<yourtag>), you have to create it through your Telegram profile settings
    press 'START' in the chat of your newly created bot (you access it by pressing on the t.me link BotFather has sent you before), it should reply to you with: 'Welcome to PC-Control bot, Use /help to see all the commands! Made by Tostapunk' and 'Keyboard is up'
    if a list of commands pops-up you have to ignor it, there's another step you have to do before you can use those commands
13. open again the console and execute the previous command (press the 'up-arrow' key on your keyboard and the command should appear in the console)
    in the small window you have to click 'Change user permissions', add your Telegram username without the '@' in the new blank field that's popped-up, then close the new even smaller window (the insert-username one) and click 'Start it' again
    your bot should has sent you a message showing: 'Bot up and running' and this is the message that informs you the remote controller is ready, but first let's do the last two steps
    now you can close the console
14. open again the console and execute the previous command
    in the small window you have to click 'Options' (at the top), 'Console', 'Hide' (by doing this the console will be invisible when executing commands from the Telegram bot), then click 'Restart' and wait for it to re-opens
    click 'Options' again, 'Startup', 'Enable' (by doing this, the remote controller will be available at every computer boot, it won't be necessary to start it again)
    close the small window
    now you can close the console
15. restart the computer again 

DONE! you've set up the remote controller successfully, your bot will send you the 'Bot up and running' message at every computer boot
you can now use the commands to remote control the computer
