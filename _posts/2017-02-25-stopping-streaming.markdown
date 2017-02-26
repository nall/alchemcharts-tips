---
layout: post
title:  "Adding the ability to Stop Streaming"
date:   2017-02-25 23:49:00 -0800
categories: streaming
---
It's often useful to have AlchemCharts stop streaming in the middle of the trading day. Maybe a candle is about to close and you don't to have to think about "line jump". Or maybe you just want to grind some during market hours and don't want the distraction of flickering quote sheets. 

AlchemCharts can stop streaming during trading hours, but it's not enabled by default. This post describes how to enable it.
+++
Enabling is pretty minor -- just adding an extra line into a file.

**NOTE** the below describes Windows 10. Other versions of Windows may differ. 

The file we care about is: `C:\Program Files\AlchemCharts\data.txt`

## Quit AlchemCharts
Before editing files it's a good idea to stop any running instance of AlchemCharts, so just quit it if it's running.

## Make a backup
It's always a good idea to make a copy of the original file before we modify it so we can restore it if things go south. I prefer just putting a copy alongside the original named data.txt.orig or something similar. 

The following just makes a copy of `data.txt` named `data - Copy.txt`.

Note that Windows will hide the `.txt` extension, so you'll probably just see `data` and `data - Copy`.

Open file explorer and navigate to `C:\Program Files\AlchemCharts`. Find the file called `data.txt` (again, might just show up as `data`) and select it by left clicking (single click). Go to the menu and choose "Home" and click the "Copy" icon. Then click "Home" and click the "Paste" icon. You'll get a dialog asking for Administrator permission. Click Continue to paste the file.

At this point you should have 2 files: `data.txt` and `data - Copy.txt`. 

Backup complete.

## Edit data.txt
Now we need to edit data.txt. Since this area is protected it means we need to edit it as an Administrator. 

The following will run the Notepad application as administrator and edit the file to add the additional line.

Press the Start button and navigate to "Windows Accessories". Find "Notepad" and right click it. Choose "More" and then click "Run as Adminstrator". Select "Yes" when prompted if this application can make changes. In Notepad, click "File" and select "Open...". Navigate to `C:\Program Files\AlchemCharts` and open `data.txt`. 

At the bottom of the file add the following line:

    stopstreaming=yes

Save the file and quit Notepad.

## Restart AlchemCharts
Now restart AlchemCharts and voila! You should have a button on the toolbar labelled "Stop Streaming". Click this during market hours and the data strema will end. Click it again to re-enable streaming. Hopefully, you now have a button like the one in the screenshot below. Enjoy!

![The final result]({{ site.baseurl }}/assets/AC_Stop_Streaming_Button.png)

