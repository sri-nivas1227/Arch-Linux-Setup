# Arch-Linux-Setup
Step by step process to setup arch linux on an existing windows laptop (HP Pavilion)

- disable secure boot
- change boot order to make the usb drive boot when connected
- iwctl to connect to internet
- archinstall to install basic setup
- setup profile and users
- install required packages for everything we need

## To-Do
- [x] setup volume controls
- [x] brigness controls
- [x] keyboard backlight
- [ ] print screen and snip screen
- [ ] rofi opens apps in a new workspace
- [ ] open nemo when show in folder is clicked
- [ ] configure clipboard

## Installing Arch on my HP Pavilion machine, replacing my Windows OS
- Backed up all data from my windows machine
- Copied Configs of arch from my removable SSD which is running Arch for now
- used a small USB and burned it with the latest Arch ISO (Sept 1 2025) versiont
- Let's goo🎉 Writing as I'm doing it
- I asked my machine to boot from the usb.
- it copies the iso into the ram and ran it. Welcome to Arch
- First step: it's time to connect to the internet with the help of iwctl
- yay, connected to the internet with few simple commands
  - `iwctl` to enter in the iwctl environment
  - `station list` to list all the network devices available to connect to the internet
  - mine gave only one, **wlan0**
  - `station wlan0 scan` to start scanning for the available wifi netowrks around me
  - `station wlan0 get-networks` to list the networks available
  - `station wlan0 connect <your-wifi-name>` as shown in the list
  - `station wlan0 show` to check if we're connected
  - exit out of iwctl
- Now, let's start our setup using a command line tool called _archinstall_
- I chose my internal storage as my primary disk for partitioning. I chose to have a dedicated /home partition and I chose LUKS encryption for my /home partition.
- I left the _Swap_ enabled
- I left the bootlader to be Systemd-boot by default
- I chose my hostname to be _ArchGuy_
- I created a use for myself with superuser permissions (so I can sudo when needed)

### Profile
- Now in the profile, I chose Desktop type so I can setup a complete hyprland environment.
- Hyprland wants to access my hardware and as hyprland has it's own polkit agent, I chose polkit over seatd
- I chose network manager for network configuration
- I added a few additional packages like

- git
- jdk 21
- nodejs
- python
- vlc
- viewnior for photos
- nemo file manager
- rofi
- hyprpaper
- hyprlock
- hyprshot (notyet)
- sddm for greeter
- dunst for notifications
- btop
- zsh
- clipse (notyet) for clipboard management
