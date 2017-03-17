# Few Usefull Things in UBUNTU 16.04

### Rename the PC
```
$ sudo gedit /etc/hostname /etc/hosts
```
Change the names in both the files and save. Restart immediately to reflect changes.


### Fix display brightness button
```
$ sudo touch /usr/share/X11/xorg.conf.d/20-intel.conf
$ sudo gedit /usr/share/X11/xorg.conf.d/20-intel.conf
```
Add the following lines to this file:
```
Section "Device"
        Identifier  "card0"
        Driver      "intel"
        Option      "Backlight"  "intel_backlight"
        BusID       "PCI:0:2:0"
EndSection
```


### Restart Wifi
```
$ sudo service network-manager restart
```


### Mount NTFS disk when Windows has hibernated in read-only mode
```
$ sudo mount -o ro /dev/sda2 /mnt
```


### Open current directory in GUI from terminal
```
$ xdg-open .
```


### Open any file as if you had double clicked it in GUI from terminal
```
$ xdg-open filename
```


### Create launchers on the Desktop
```
$ sudo apt install gnome-panel
$ gnome-desktop-item-edit --create-new ~/Desktop
```


### CTRL+ALT+DEL
Add custom keyboard shortcut: `gnome-system-monitor`


### Sticky Notes
```
$ sudo apt install xpad
```


### Offline Documentation Browser
```
$ sudo apt-get install zeal
```


### Snipping tool on Ubuntu
```
$ sudo add-apt-repository ppa:shutter/ppa
$ sudo apt-get update
$ sudo apt-get install shutter
```


### Install Skype
Canonical Partners should be enabled
```
$ sudo apt install skype
```


### Enable ‘Minimise on Click’
```
$ gsettings set org.compiz.unityshell:/org/compiz/profiles/unity/plugins/unityshell/ launcher-minimize-window true
```


### Move The Unity Launcher
```
$ gsettings set com.canonical.Unity.Launcher launcher-position Bottom
```


### Fix 'WiFi constantly disconnects' problem
Make sure that power management is turned off
```
$ iwconfig
```
This should display a line with Power Management: Off. If it says On, you have to run:
```
$ sudo iwconfig wlan0 power off
```


### Install Vivaldi web browser
```
$ echo "echo deb http://repo.vivaldi.com/stable/deb/ stable main > /etc/apt/sources.list.d/vivaldi.list" | sudo sh
$ curl http://repo.vivaldi.com/stable/linux_signing_key.pub | sudo apt-key add - sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 1397BC53640DB551
$ sudo apt-get update
$ sudo apt-get install vivaldi-stable
```


### Install Brackets.io web dev editor
```
$ sudo add-apt-repository ppa:webupd8team/brackets
$ sudo apt-get update
$ sudo apt-get install brackets
```


### Scheduling a shutdown
Wait 60 mins before starting the shutdown sequence
```
$ sudo shutdown -P +60
```
To shutdown at 1 AM
```
$ sudo shutdown -P 1:00
```
To shutdown now
```
$ sudo shutdown -P now
```
Cancel a pending shutdown
```
$ sudo shutdown -c
```