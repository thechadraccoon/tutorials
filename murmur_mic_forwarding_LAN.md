These are the actions that are required to make Mumble mic forwarding a thing.

This is a Windows only guide, sadly, as VBCable is a Windows only utility.

Although Linux and Mac OS could potentially work with loop devices.
___

When I refer to the host PC, I mean the one which runs GFE / Sunshine / Open-stream.

When I refer to the client PC, I mean the one which runs moonlight.

## Setup Murmur ( host )

*  Download Mumble from [their site](https://www.Mumble.info/).

* Run the installer.

* Enable the server feature as shown in the screenshots.
  
  ![installer_server_feature_off](https://user-images.githubusercontent.com/11398266/118360306-ff4c4180-b554-11eb-9cba-6974ba8f0bed.png)
  ![installer_server_feature_on](https://user-images.githubusercontent.com/11398266/118360316-0d01c700-b555-11eb-928d-29e331e27e74.png)

* Launch Murmur.

  ![start_menu_Murmur](https://user-images.githubusercontent.com/11398266/118360334-1be87980-b555-11eb-93d8-d552d0acb226.png)

* Accept firewall exception.
  Otherwise, you won't be able to connect to it.

  ![firewall_allow_Murmur](https://user-images.githubusercontent.com/11398266/118360344-26a30e80-b555-11eb-88bd-2fa9fc6c87ef.png)


* Check the system tray for the icon.
That means the server side is up and running.

  ![Murmur_tray_icon](https://user-images.githubusercontent.com/11398266/118360376-39b5de80-b555-11eb-96c0-40ab4f845817.png)

* Make Murmur start with your PC.
  * Go to the Mumble installation folder. (Default is C:\Program Files\Mumble on Windows)
  * Locate Murmur.exe in the folder.
  * Right-click it.
  * Select create shortcut.
  * Answer yes to the prompt. (It creates the shortcut on the desktop instead of folders as you don't have the permissions)
  * Now press Windows key + R.
  * Type in ```%appdata%\Microsoft\Windows\Start Menu\Programs\Startup``` (This opens a folder in which you can put shortcuts that will be executed upon logging on).
  * Next, drag the Murmur shortcut from your desktop into the folder.
  * Congrats! Murmur now starts with your PC!
* Grab the host's internal IP.
  * Press Windows key + R.
  * Type in ```cmd```. 
  * Press enter. (This opens a DOS-like terminal.)
  * Type ```ipconfig```.
  * Press enter.
  * Write down the IPv4 Address. (This will be important later)

    ![cmd_ipconfig](https://user-images.githubusercontent.com/11398266/118362915-d3828900-b55f-11eb-971b-f71f032a66b3.png)
-----
# Setup Mumble ( host )

* Download VBCable from [their site] (https://vb-audio.com/Cable/).
* Install it. [[Guide](https://www.howtogeek.com/364369/how-to-record-your-pcs-audio-with-vb-cable/), Don't do the listening part.]
* Run Mumble client and set it up.
  * You want it to have its sound output on VBCable.
  * I recommend without push to talk, minimal noise gate (so it doesn't permanently transmit)
* When you launch it, it will ask you to which server you want to connect.
  * Click on add new.
  * In the address field, type ```127.0.0.1```.
  * In the username field type a name. This will be the host's name in the voice channel. ( I use ```serv``` here )
  * In the Label field, type a nickname for it. ( mine is ```racc's comms``` )
* Add auto-connect.
  * Click on Configure at the top of the main window.
  * Select settings.
  * Go to the Network tab.
  * Tick the "Reconnect to last server on startup".
* Make it start with PC.
  * Press Windows key + R.
  * Type in ```%appdata%\Microsoft\Windows\Start Menu\Programs\Startup``` (This opens a folder in which you can put shortcuts that will be executed upon logging on).
  * Next, copy the Mumble shortcut from your desktop into the folder.
  * Congrats Mumble starts with your PC!
-----

# Setup Mumble ( client )

* Download Mumble from [their site](https://www.Mumble.info/).
* Run the installer. But don't enable Murmur.
* Run Mumble, set it up.
  * Don't enable push to talk. It becomes a hassle when you play games with different push to talk configurations. 
    * Push to talk should be setup in-game as if you were on that PC.
  *  Make it voice activated with a noise gate. 
* When you launch it, it will ask you to which server you want to connect.
  * click on add new.
  * In the address field, type ```127.0.0.1```.
  * In the username field type a name. This will be the host's name in the voice channel. ( I use ```serv``` here. )
  * In the Label field, type a nickname for it. ( mine is ```racc's comms``` )
* Add auto-connect.
  * Click on Configure at the top of the main window.
  * Select settings.
  * Go to the Network tab.
  * Tick the "Reconnect to last server on startup".
-----

This is how I achieved LAN mic forwarding using Mumble's software.