This requires either portforwading the Murmur server port directly (Discouraged) or a [Wireguard vpn](https://github.com/thechadraccoon/tutorials/blob/main/resource_wireguard_setup.md) (Recommended)

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

___
# Setup Mumble ( host )

This is the same as in the [LAN](https://github.com/thechadraccoon/tutorials/blob/main/murmur_mic_forwarding_LAN.md) setup.
___

# Setup Mumble ( client )

* Download Mumble from [their site](https://www.Mumble.info/).
* Run the installer. But don't enable Murmur.
* Run Mumble, set it up.
  * Don't enable push to talk. It becomes a hassle when you play games with different push to talk configurations. 
    * Push to talk should be setup in-game as if you were on that PC.
  *  Make it voice activated with a noise gate. 
* When you launch it, it will ask you to which server you want to connect.
  
* if port forwarding:
    * Grab the host's external IP. ( on the host )
        * Press Windows key + R.
            * Type in ```cmd```. 
                * Press enter. (This opens a DOS-like terminal.)
        * Type ```curl ifconfig.me```.
            * Press enter.
        * Write down the numbers.
    * click on "add new". ( on client )
        * In the address field, type the IP of the host. ( Google's is ```8.8.8.8``` )
        * In the username field type a name. This will be the host's name in the voice channel. ( I use ```client1``` etc. here. )
        * In the Label field, type a nickname for it. ( mine is ```racc's comms``` )
* If using the Wireguard solution:
    * click on "add new".
        * In the address field, type the wireguard IP of the host. (Mine is ```10.7.0.2```)
        * In the username field type a name. This will be the host's name in the voice channel. ( I use ```client1``` etc. here. )
        * In the Label field, type a nickname for it. ( mine is ```racc's comms``` )
* Add auto-connect.
  * Click on Configure at the top of the main window.
  * Select settings.
  * Go to the Network tab.
  * Tick the "Reconnect to last server on startup".
-----

This is how I achieved WAN mic forwarding using Mumble's software.