These are the actions that are required to make mumble mic forwarding a thing. 
This is a Windows only guide sadly as vbcable is a Windows only utility.
Altough linux and could potentially work with loop devices.

When I refer to the host PC, I mean the one which runs GFE / Sunshine / Open-stream.

When I refer to the client PC, I mean the one which runs moonlight.


## Setup murmur ( host )

*  Download Mumble from [their site](https://www.mumble.info/).

* Run the installer.

* Enable the server feature as shown with screenshot.
  
  ![installer_server_feature_off](https://user-images.githubusercontent.com/11398266/118360306-ff4c4180-b554-11eb-9cba-6974ba8f0bed.png)
  ![installer_server_feature_on](https://user-images.githubusercontent.com/11398266/118360316-0d01c700-b555-11eb-928d-29e331e27e74.png)


* Launch murmur.

  ![start_menu_murmur](https://user-images.githubusercontent.com/11398266/118360334-1be87980-b555-11eb-93d8-d552d0acb226.png)

* Accept firewall exception.
  * Otherwise you won't be able to connect to it.

  ![firewall_allow_murmur](https://user-images.githubusercontent.com/11398266/118360344-26a30e80-b555-11eb-88bd-2fa9fc6c87ef.png)


* Check system tray for icon.
That means the server side is up and running.

  ![murmur_tray_icon](https://user-images.githubusercontent.com/11398266/118360376-39b5de80-b555-11eb-96c0-40ab4f845817.png)

* Make murmur start with PC.
  * Go to the mumble installation folder. ( Default is C:\Program Files\Mumble on windows )
  * Locate murmur.exe in the folder.
  * Right-click it.
  * Select create shortcut.
  * Answer yes to the prompt. ( it creates the shortcut on desktop instead of folder as you don't have the permissions )
  * Now press windows key + r.
  * Type in %appdata%\Microsoft\Windows\Start Menu\Programs\Startup ( this opens a folder in which you can put shortcuts the will be executed upon loging on )
  * Next drag the murmur shortcut from desktop into the folder.
  * Congrats! murmur starts with PC!
* Grab the host's internal IP.
  * Press windows key + r.
  * type in cmd. ( this opens a terminal )
  * type ipconfig.
  * press enter.
  * Write down the IPv4 Adress. ( this will be important later )
    ![cmd_ipconfig](https://user-images.githubusercontent.com/11398266/118362915-d3828900-b55f-11eb-971b-f71f032a66b3.png)


-----
# Setup Mumble ( host )

* Download VBCable from [their site](https://vb-audio.com/Cable/).
* Install it. [[Guide](https://www.howtogeek.com/364369/how-to-record-your-pcs-audio-with-vb-cable/), Don't do the listen part.]
* Run mumble client and set it up without push to talk, minimal noise gate (so it doesn't permanently transmit) and for it to have its sound output on vbcable.
* When you launch it will ask you to which server you wish to connect.
  * click on add new.
  * In the address field, type 127.0.0.1
  * Type a name in the username field ( I use serv )
  * In the Label field, type a nickname for it. ( mine is racc's comms )
* Add auto-connect.
  * Click on Configure at the top of the main window.
  * Select settings.
  * Go to the Network tab.
  * Tick the "Reconnect to last server on startup".
* Make it start with PC.
  *  Press windows key + r.
  *  Type in %appdata%\Microsoft\Windows\Start Menu\Programs\Startup ( this opens a folder in which you can put shortcuts the will be executed upon loging on ).
  *  Next copy the Mumble shortcut from desktop into the folder.
  *  Congrats Mumble starts with PC!
-----

# Setup Mumble ( client )

* Download Mumble from [their site](https://www.mumble.info/).
* Run the installer. But don't enable murmur.
* Run mumble, set it up. Don't enable push to talk. Just do voice activated with noise gate. ( push to talk will be setup in-game as if you were on that pc. )
* When you launch it will ask you to which server you wish to connect.
  * click on add new.
  * In the address field, type the IPv4 you wrote down during murmur setup. ( mine would be 192.168.1.20 )
  * Type a name in the username field ( I use client1 etc. )
  * In the Label field, type a nickname for it. ( mine is racc's comms )
* Add auto-connect.
  * Click on Configure at the top of the main window.
  * Select settings.
  * Go to the Network tab.
  * Tick the "Reconnect to last server on startup".
-----

This is how I achieved mic forwarding using mumble's software.

This can be adapted to work throught WAN but I've never had to do it.
