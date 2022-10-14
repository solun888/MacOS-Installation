# How to Turn off Google Chrome Automatic Updates in Mac OS X.
This works to prevent Google Chrome from automatically updating itself in Mac OS X:

Launch the Terminal, found in / Applications / Utilities /
Enter the following default write command and press return:

Defaults write com. google.Keystone.Agent checkInterval 0

Exit Terminal and restart Google Chrome
Remember that this will disable all automatic updates for all Google applications on the computer, not just Chrome. There may be a way to just turn off Chromes auto-updating, but I haven’t found it, even Google offers the broader solution described above.

