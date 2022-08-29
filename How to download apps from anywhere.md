# How to download apps from anywhere


Before macOS Sierra, it was much easier to download apps from anywhere. You’d simply go to System Preferences > Security & Privacy > General, then under Allow apps to be downloaded from, select Anywhere.

However, since new updates to macOS, you’ll need to change a few more settings on your Mac. Here’s what you should do:

1. Launch Terminal by going to Finder > Applications > Utilities. You can also locate it with Spotlight search by pressing Command-Space.
1. In Terminal, type the command ```spctl --global-enable``` and hit Return. Enter your Mac’s password.
1. Go to System Preferences > Security & Privacy > General. At the bottom of the window, you’ll see Allow apps to be downloaded from with automatically selected Anywhere.


If you later decide that you’d like to return to your Mac’s default settings and no longer allow apps to be downloaded from anywhere, just follow these steps:

Launch Terminal.
Then, enter the command ```sudo spctl --global-enable```. 
By doing that, you’ll no longer be able to select Anywhere. So after it’s done, you will only be allowed to download apps from the App Store unless you use the steps mentioned above to access apps from other locations.


(Link)[https://macpaw.com/how-to/allow-apps-anywhere#:~:text=Enter%20your%20Mac's%20password.,from%20with%20automatically%20selected%20Anywhere.]
