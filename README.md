# VLC_as_Root
Run VLC as root on  Linux.

### By Byron Taaka

For security reasons, VLC does not run on root by default.<br/>
However, if you still want to run VLC as root,
You can follow these 'One-Time' Steps:

0. **check whether VLC can run as root**, via Terminal or FileManager

1. **Get the Absolute path to our VLC** using 'which' command:<br/>`which vlc`
	<br/>in my case and probably Yours, the path is **/usr/bin/vlc**

2. **Backup the vlc** (optional in case you trust yourself)
		`cp /usr/bin/vlc /usr/bin/vlc.bkp`

3. **Open the vlc with the hexeditor**<br/>
		`hexeditor /usr/bin/vlc`

4. **Search for 'geteuid'**<br/>
Press `ctrl + w` to search.<br/>
select '_search for text string_' and Press `ENTER` to search

5. **Replace 'geteuid' with 'getppid'**<br/>
	Press the `tab` button to switch from hex to text as we want to edit the text instead of the Hex

6. **Save &amp; exit.**<br/>
	Press `ctrl + x`

### **We Are Done!**<br/>
### **Now You can Enjoy VLC on root.**


## **Undoing Changes:**
### 7. **Exit Without Saving**<br/>
Press `ctrl + c` to exit hexeditor without saving the changes you've made to VLC.

### 8. **Restore Original VLC**<br/>
In case You change your mind about this,<br/>
	you can replace the **getppid** with **geteuid**,<br/>
	or<br/>
	Restore the VLC backup with:<br/>
			`cp /usr/bin/vlc.bkp /usr/bin/vlc`

## **Note:**
Upon upgrading VLC, You will need to ReDo steps `1-6`.
