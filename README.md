                        # Few Usefull Things in UBUNTU 16.04

### Development
    
Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantanously see your updates!

Open your favorite Terminal and run these commands.

First Tab:
```sh
$ sudo gedit /usr/share/X11/xorg.conf.d/20-intel.conf
```



#### Rename the PC:
```sh
$ sudo gedit /etc/hostname /etc/hosts
```
Change the names in both the files and save. Restart immediately to reflect changes.


#### Fix display brightness button:
```sh
$ sudo touch /usr/share/X11/xorg.conf.d/20-intel.conf
$ sudo gedit /usr/share/X11/xorg.conf.d/20-intel.conf
```
Add the following lines to this file:
```sh
Section "Device"
        Identifier  "card0"
        Driver      "intel"
        Option      "Backlight"  "intel_backlight"
        BusID       "PCI:0:2:0"
EndSection
```

#### Restart Wifi:
```sh
sudo service network-manager restart
```

#### Mount NTFS disk when hibernated in read-only mode:
```sh
sudo mount -o ro /dev/sda2 /mnt
```

#### Open current directory in GUI from terminal:
```sh
xdg-open .
```

#### Open any file as if you had double clicked it in GUI from terminal
```sh
xdg-open filename
```

#### Create launchers on the Desktop
```sh
sudo apt install gnome-panel
gnome-desktop-item-edit --create-new ~/Desktop
```

#### CTRL+ALT+DEL
```sh
add custom keyboard shortcut: gnome-system-monitor
```

#### Sticky Notes
```sh
sudo apt install xpad
```

#### Offline Documentation Browser
```sh
sudo apt-get install zeal
```

#### Snipping tool on Ubuntu
```sh
sudo add-apt-repository ppa:shutter/ppa
sudo apt-get update
sudo apt-get install shutter
```

#### Install Skype
```sh
Canonical Partners should be enabled
sudo apt install skype
```

#### Enable ‘Minimise on Click’
```sh
gsettings set org.compiz.unityshell:/org/compiz/profiles/unity/plugins/unityshell/ launcher-minimize-window true
```

#### Move The Unity Launcher:
```sh
gsettings set com.canonical.Unity.Launcher launcher-position Bottom
```

#### WiFi constantly disconnects:
Make sure that power management is turned off
```sh
iwconfig
```
This should display a line with Power Management: Off. If it says On, you have to run:
```sh
sudo iwconfig wlan0 power off
```

#### nstall Vivaldi web browser:
```sh
echo "echo deb http://repo.vivaldi.com/stable/deb/ stable main > /etc/apt/sources.list.d/vivaldi.list" | sudo sh
curl http://repo.vivaldi.com/stable/linux_signing_key.pub | sudo apt-key add -
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 1397BC53640DB551
sudo apt-get update
sudo apt-get install vivaldi-stable
```

#### Install Brackets.io web dev editor
```sh
sudo add-apt-repository ppa:webupd8team/brackets
sudo apt-get update
sudo apt-get install brackets
```

#### Scheduling a shutdown

sudo shutdown -P +60
That will wait 60 mins before starting the shutdown sequence.

sudo shutdown -P 1:00
to shutdown at 1 AM

to shutdown now
sudo shutdown -P now

Cancel a pending shutdown
```sh
sudo shutdown -c
```
