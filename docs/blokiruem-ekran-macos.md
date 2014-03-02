#1 способ:#

##Creating a Service##

Open ‘Automator’ from your ‘Applications’ folder
When asked to choose a type for your document, pick ‘Service’ and proceed
From the library of actions (left side), choose ‘Run AppleScript’ from ‘Utilities’ and drag it to the right side of the window
Make sure you chose ‘Service receives no input in any application‘ in the drop-down menu on the top
Replace (* Your script goes here *) with the following code:
`do shell script "'/System/Library/CoreServices/Menu Extras/User.menu/Contents/Resources/CGSession' -suspend > /dev/null"
return input`
Save everything under a name of your choice (it will reside in~/Library/Services from now on)
Assigning a shortcut

Open ‘Keyboard’ from the ‘System Preferences’
Go to the ‘Keyboard Shortcuts’ tab and choose ‘Services’ on the left side
Somewhere near the end of the list that shows on the left side, some service with the name you chose when saving your service from Automator will show up
Double click on the far right side of that services name and you can assign a keyboard shortcut of your choice (I chose Ctrl+CMD+L)
Close ‘System Preferences’
That’s it. Now you can easily lock your mac with a keyboard shortcut of your choice without being annoyed by having to type in your password every time your display goes to sleep our your screensaver starts.
 
2 способ:

Блокируем экран через терминал

Если вы часто работаете в терминале, вы можете создать для себя shell-скрипт, переводящий Mac OS X в режим входа в систему, не завершая при этом запущенных приложений. Достаточно запустить Терминал и выполнить там строчку
echo -e \#\!/bin/sh\ «\n»/System/Library/CoreServices/Menu\\ Extras/User.menu/Contents/Resources/CGSession\ -suspend > ~/lock.command && chmod 755 ~/lock.command
после чего в вашей домашней директории появится shell-скрипт с именем lock.command, запуская который вы мгновенно заблокируете систему.
Расширение .command используется для того, чтобы этот скрипт можно было запускать не только из терминала, но и из среды Finder.
 
3 способ:

Заходим в System Preferences > Security и активируем параметр Require password, в поле значения выбираем immediately.
По нажатию системного сочетания клавиш Ctr+Shift+open_disk мак будет «засыпать», а при пробуждении будет спрашивать пароль.