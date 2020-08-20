# How to set a keyboard shortcut to run a batch script or any executable file using windows.

The example is a shortcut to extend display to another monitor and to show only on main display using the keys Ctrl + Alt + Down and Ctrl + Alt + Up respectively. 

This tool is pretty powerful because you can link anything that is executable up to a keyboard shortcut. For example I can run cmd using the shortcut Ctrl+Alt+c that is much faster than win+r, "cmd", enter. Also you can open up .bat scripts that you have written to do things like open git and pull all your individual repos to update or have a key set for each machine you RDP into. 

 [***Skip to here if you are tech savvy and don't need detailed instructions***](#Quick-Shortcut-Guide)

## How to create an executable batch script

If you have trouble or don't want to write the bat scripts they can be found [**here**.](https://github.com/DIYCharles/r-keyboardshortcuts/tree/master/Creating%20bat%20Shortcuts/batScripts) A general rule of thumb is never download and run any .bat file without knowing the contents and that it is from a trusted host. Regardless, I've uploaded them anyways.

On your desktop right click then click new then text document. You can leave the name to whatever because we will change it later.

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img1.JPG "img1.jpg")

Open the .txt file in notepad.

The batch files we are creating are going to run in the command line and will either extend the display to another monitor or show only on the main monitor. Here is the first code we are going to write that extends your display

```batch

echo "hello"

%windir%\System32\DisplaySwitch.exe /extend
```

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img2.JPG "img2.jpg")

Save the .txt file and exit notepad.

Right click the .txt file and click rename. Delete the whole name including the .txt at the end. Rename it to ExtendDispalys.bat . The name is not important but the .bat file extension is. After you rename it you should get and error like this.

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img3.JPG "img3.jpg")

If the file is renamed to ExtendDisplays.txt you need to rename and make sure you delete the .txt and add .bat at the end.

Double click the .bat file to run it and see if it works. If it works you will see this pop up at the edge of your screen.

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img81.jpg "img81.jpg")

The next batch script will make the computer only display on the main screen. You will follow the same steps as above to write and save then rename it ShowOnlyOnOne.bat (again name is not important as long as it has .bat at the end) Here is the code for it

```batch
echo "hello"

%windir%\System32\DisplaySwitch.exe /internal
```

Check to make sure both .bat files run as intended. They should look like this when done.

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img4.JPG "img4.jpg")

## Creating a keyboard shortcut to run the scripts

For some reason my shortcuts will only run when both the script and shortcut are on my desktop in C:\Users\Charles\Desktop\

Right click your ExtendDispalys.bat file and click create shortcut. Do this for both .bat files.

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img5.JPG "img5.jpg")

Right click on the shortcut icon that was created and click properties

In the shorcut tab go down to the shorcut key. I am going to set this to Ctrl + Alt + Down because my secondary monitor is below my main monitor. Click apply and exit properties. It should look like this.

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img6.JPG "img6.jpg")

Test the shortcut to make sure it works

Repeat this for the ShowOnlyOnOne.bat shortcut. I set it to Ctrl + Alt + up .

![alt text](https://raw.githubusercontent.com/DIYCharles/r-keyboardshortcuts/master/Creating%20bat%20Shortcuts/photos/img7.JPG "img7.jpg")

Test both shortcuts and enjoy!

# Quick Shortcut Guide

1. Create an ExtendDisplays.bat file with the following code. The name is not important as long as it is a .bat file

```batch
echo "hello"

%windir%\System32\DisplaySwitch.exe /extend
```

2. Create another named ShowOnlyOnOne.bat with the following code.

```batch
echo "hello"

%windir%\System32\DisplaySwitch.exe /internal
```

3. Move these files to C:/Users/YOURUSERNAME/Desktop
4. Right click and select make shortcut for each .bat files
5. Right click on the shortcut icon and select properties
6. Under the shortcut tab locate the shortcut key
7. Enter in a combo of Ctrl+Alt+(desired key) *For example I used Ctrl+Alt+down to extend displays*
8. Click apply and close then double check by going to properties that the shortcut saved
9. Test the shortcut by clicking Ctrl+Alt+(desired key). It should work in every window all the time. 
