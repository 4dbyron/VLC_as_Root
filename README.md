# VLC_as_Root
Run VLC on Linux as Root

### By Byron Taaka

For security reasons, VLC does not run on Linux as root by default.<br/>
However, if you really need to run VLC when logged in as root.<br/>

[You can watch this video](https://youtu.be/vsOxSU4Qgjg) <br/>or <br/>
Follow this '_One-Time_' procedure:

0. **check whether VLC can run as root**, via Terminal or FileManager

1. **Get the Absolute path to our VLC** using the 'which' command:<br/>`which vlc`
	<br/>in my case and probably Yours, the resulting path is **/usr/bin/vlc**

2. **Backup the vlc** (optional in case you trust yourself)<br/>
		`cp /usr/bin/vlc /usr/bin/vlc.bkp`

3. **Open the vlc with the hexeditor**<br/>
		`hexeditor /usr/bin/vlc`

4. **Search for 'geteuid'**<br/>
Press `ctrl + w` to search.<br/>
Once the search dialog is displayed,<br/>
You can press `A` for _text_ search,<br/> or<br/>
select '_search for text string_' and Press `ENTER` to search

5. **Replace 'geteuid' with 'getppid'**<br/>
	Press the `tab` button to switch from hex to text as it is easier to edit plain text than Hex.

6. **Save &amp; exit.**<br/>
	Press `ctrl + x`

### **We Are Done!**<br/>
### **Now You can Enjoy VLC on root.**

<hr/>
<hr/>

## **Undoing Changes:**
### 7. **Exit Without Saving**<br/>
Press `ctrl + c` to exit the hexeditor without saving the changes you've made to VLC.

### 8. **Restore Original VLC**<br/>
In case You change your mind about running vlc as root,<br/>replace the **getppid** with **geteuid**,<br/>
	or<br/>
	Restore the VLC backup with:<br/>
			`cp /usr/bin/vlc.bkp /usr/bin/vlc`

<hr/>
## **Note:**
- Upon upgrading VLC, You will need to ReDo steps `1-6`.
- hexeditor comes preinstalled in most Linux/Unix-Like distributions.
- All the hexeditor commands / shortcuts used here are displayed at the bottom of the hexeditor screen whenever applicable.
