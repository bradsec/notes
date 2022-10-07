## debian setup notes

Topics: [[debian]]  

---
# Debian Linux (including Kali, Ubuntu, PopOS)<br>Installation Notes, Hints & Tips

## Install Common Utilities and Applications
- Most applications below require a desktop environment installed such as GNOME, LXDE etc.
- Later versions of Debian or Ubuntu (Ubuntu 20.04+) should not require additional apt sources to install the packages listed below.
- Copy and paste the commands below directly into a terminal to batch install the applications if required.
- Other Debian applications which require more configuration to install have added to the [bradsec/bashscripts](https://github.com/bradsec/bashscripts) repo and have simple installation menu options.

```terminal
# Network and system terminal CLI tools
sudo apt-get -y install net-tools curl wget nmap htop

# Development and version control tools
sudo apt-get -y install git

# Add kernel and module build tools
sudo apt-get -y install build-essential dkms linux-headers-$(uname -r)

# Add additional make tools
sudo apt-get -y install sassc gettext

# Python3 and pip3
sudo apt-get -y install python3 python3-pip python3-gpg 
pip3 install --upgrade pip
pip3 install setuptools

# Text editor tools
sudo apt-get -y install vim

# Disk partition tools
sudo apt-get -y install gparted 

# Backup tools
sudo apt-get -y install timeshift

# Privacy and system management tools
sudo apt-get -y install bleachbit
sudo apt-get -y install stacer

# File archive compression tools
sudo apt-get -y install rar unrar

# Image editor tools
sudo apt-get -y install gimp
sudo apt-get -y install inkscape

# Terminal image viewer
sudo apt-get -y install feh

# Screenshot Screen Capture and Recording tools
sudo apt-get -y install flameshot
sudo apt-get -y install kazam

# Audio file tools
sudo apt-get -y install audacity

# Video player, tools and codecs
sudo apt-get -y install vlc
sudo apt-get -y install handbrake
sudo apt-get -y install ffmpeg
sudo apt-get -y install libavcodec-extra gstreamer1.0-libav gstreamer1.0-plugins-ugly gstreamer1.0-vaapi

# Add additional fonts
sudo apt-get -y install ttf-mscorefonts-installer
sudo apt-get -y install fonts-crosextra-carlito fonts-crosextra-caladea
sudo apt-get -y install ttf-bitstream-vera
sudo apt-get -y install fonts-firacode -y

# Update, Upgrade, and Cleanup and Fix Broken Installs
sudo apt-get update
sudo apt-get -y dist-upgrade
sudo apt-get -y autoremove
sudo apt-get -y autoclean
sudo apt-get -y install --fix-broken
```

## GNOME Specific Improve Desktop Appearance
```terminal
# Install GNOME tweaks
sudo apt-get -y install gnome-tweaks
```

### GNOME Extensions
- https://extensions.gnome.org
- Add browser extension (works with Firefox or Chrome)
  - Activate - User Themes
  - Activate - Dash-to-Dock
- Additional settings under Tweaks applcation
  - Appearance and Extensions tabs

### Improve desktop appearance with improved themes/icons

```terminal
# Install Orchis-theme and papirus-icon-theme
sudo apt-get -y install papirus-icon-theme
git clone https://github.com/vinceliuice/Orchis-theme.git
./Orchis-theme/install.sh 

# Apply the themes
gsettings set org.gnome.desktop.interface gtk-theme Orchis-Dark
gsettings set org.gnome.desktop.wm.preferences theme Orchis-Dark
gsettings set org.gnome.shell.extensions.user-theme name Orchis-Dark
gsettings set org.gnome.desktop.interface icon-theme Papirus

# Set background to solid RGB color
gsettings set org.gnome.desktop.background picture-uri ''
gsettings set org.gnome.desktop.background primary-color 'rgb(18, 108, 210)'
```

## Simple UFW firewall with GUI management
```terminal
sudo apt-get -y install ufw gufw
sudo ufw enable
```

## Laptop Specific - Power Management
```terminal
sudo apt-get -y install tlp-get -y
```

## Ubuntu Specific
```terminal
sudo apt-get -y install ubuntu-restricted-extras
```

## NVidia Graphics Specific
```terminal
sudo apt-get -y install nvidia-detect
sudo nvidia-detect
sudo apt-get -y install nvidia-driver
```

## File manager show dotfiles or hidden files
Shortcut `ctrl-h`

## Debian microcode
- Open Synaptic Package Manager
- Search "microcode"
- Install appropriate microsoft AMD or Intel

## Debian enable snap and flatpak support
- Open "Software" application
- Search in Software application for "software"
- Click "Software"
- Scroll down to Add-ons and select Flatpak and Snap Support

## Debian Swappiness
- If system has increased memory number can be reduced and may improve performance.
- Check current (default 60)  
`cat /proc/sys/vm/swappiness`
- Modify by editting the /etc/sysctl.conf and add line below and reboot.  
`vm.swappiness=10`

## Debian Increase Boot Speed'
- Edit grub loader `/etc/default/grub` and modify timeout from 5 to 0  
`GRUB_TIMEOUT=0`
- Alternatively copy and paste the sed replacement command below:
```terminal
sudo sed -i 's/GRUB_TIMEOUT=5/GRUB_TIMEOUT=0/g' /etc/default/grub
```

- Update GRUB and reboot to test  
`sudo update-grub`

## Create home directories
```bash
mkdir ~/.themes
mkdir ~/.icons
```

# Debian Distro Minimal Install Notes

When prompted unselect all desktop and package options *(use mouse with graphical install or spacebar to unselect normal install)*. The base install should boot to a terminal as no X Window desktop environment should have been selected.

### `sudo` command not found and/or default user not in the sudo group

***When installing is you leave root password blank this should disable the root account and install sudo for the user you create. Otherwise follow the steps below to enable sudo on a selected user account.***

The mimimal install may mean the `sudo` command may not be installed.
The following commands install the sudo package and adds the default (logged in user) to the sudo group.

```terminal
su -c 'apt-get update && apt-get -y install sudo && \
/sbin/usermod -aG sudo $USER && \
exec su -l $USER'
```

To undo the above (remove user from group sudo and remove package sudo) run the following:  
```terminal
su -c 'gpasswd -d $USER sudo && \
apt-get -y remove sudo && exec su -l $USER'
```

### Updating Debian
```terminal
sudo apt-get update && sudo apt-get -y dist-upgrade
```

### Debian base install - ifconfig, shutdown, reboot, halt and other commands not working

It may be that `/sbin` is missing from the user $PATH variable  
To check current path variables run:
- `echo $PATH` or `env | grep PATH`

Simply edit the `/etc/profile` file and append `/sbin` to the second PATH variable.
- Using nano `sudo nano /etc/profile`
- Using vi `sudo vi /etc/profile`  

*You may need to logout and back in to initialize the new PATH variables.*

Alternatively use the direct path

```terminal
sudo /sbin/reboot
sudo /sbin/halt
sudo /sbin/shutdown
```

Alternatively use the systemctl commands as follows:

```terminal
sudo systemctl reboot
sudo systemctl halt
sudo systemctl poweroff
```

### Install GNOME Desktop Environment (core only, no games, office apps etc.)

```terminal
sudo apt-get -y install gnome-core
```

### Install XFCE Desktop Environment
```terminal
sudo apt-get -y install xserver-xorg xfce4 xfce4-goodies
```

### Check boot environment graphical or console/terminal
```terminal
sudo systemctl get-default
```

### Start in graphical environment

```terminal
sudo systemctl set-default graphical.target
```

### Start in terminal/console environment

```terminal
sudo systemctl set-default multi-user.target
```

# SSH Notes

### Install SSH server (Debian base install)

```terminal
sudo apt-get -y install openssh-server
```

### Backup and Regenerate SSH Server Keys (Debian/Kali)

```terminal
sudo mkdir /etc/ssh/backup_keys && \
sudo mv /etc/ssh/ssh_host_* /etc/ssh/backup_keys && \
sudo dpkg-reconfigure openssh-server
```  

# Miscellaneous Notes

### Networking - Show active ports and processes

```terminal
# Command switches [a] all, [t] TCP, [u] UDP, [l] listening, [p] process, [n] numeric 
# Using netstat command
netstat -laptun

# Using ss command
ss -laptun

# Resolve IP addresses
ss -laptur
```

### Disable IPV6 on all interfaces
```terminal
sudo nano /etc/sysctl.conf
```
Add the following line to ```sysctl.conf```:  
`net.ipv6.conf.all.disable_ipv6 = 1`  
*Change all to interface adapter name for individual interfaces*  
Run ```sudo sysctl -p``` to execute changes

### Missing firmware (Debian base install)
Check ```/etc/apt/sources.list``` contains ```contrib non-free``` otherwise edit the file append to end of each deb source line and run the following commands.

If `sources.list` is missing contrib non-free:  
```terminal
sudo sed -r -i 's/^deb(.*)$/deb\1 contrib non-free/g' /etc/apt/sources.list
```  

```terminal
sudo apt-get update && sudo apt-get -y install firmware-misc-nonfree
```

If wifi drivers such those in some Intel NUCs are missing try...

```terminal
sudo apt-get -y install firmware-iwlwifi
```

### Install ZSH shell
```terminal
sudo apt-get -y install zsh
```

### Change default user shell to zsh (don't use sudo)  
```terminal
chsh -s $(which zsh)
```

### Load existing `.profile` PATHS etc. while using ZSH
Edit `~/.zshrc` and append the following to end of file
```terminal
[[ -e ~/.profile ]] && emulate sh -c 'source ~/.profile'
```

### Check current user shell
```terminal
ps -p $$
```

### Custom prompt for ZSH shell
Edit `~/.zshrc` and edit or add the following
```terminal
PROMPT=$'\n%F{%(#.blue.cyan)}┌──${debian_chroot:+($debian_chroot)─}${VIRTUAL_ENV:+($(basename $VIRTUAL_ENV))─}(%B%F{%(#.blue.green)}%n%B%F{%(#.blue.white)}@%B%F{%(#.blue.cyan)}%m%b%F{%(#.blue.cyan)})-%b%F{%(#.blue.green)}[%B%F{%(#.blue.white)}%(6~.%-1~/…/%4~.%5~)%b%F{%(#.blue.green)}]%b%F{%(#.blue.cyan)}\n└─$ %b%F{reset}'
```
Prompt Result 
```terminal

┌──(user@machinename)-[/current_path/]
└─$ 
```

### Fix slow lagging VNC and VNC resolution issues on headless Raspberry Pi 4
Edit `/boot/config.txt`
```terminal
#### Comment out the following lines
# Enable DRM VC4 V3D driver
#dtoverlay=vc4-kms-v3d
#max_framebuffers=2

#### Uncomment this line
hdmi_force_hotplug=1

#### Uncomment and modify the following two lines to force higher resolution
# uncomment to force a specific HDMI mode (this will force VGA)
hdmi_group=2
hdmi_mode=82
```

### GNU Privacy Guard (GPG)

- Generate new key
```terminal
gpg --full-generate-key

# Select default key RSA and RSA
# Increase key security/length to 4096
# Set key expiry 0 = Does not expire
# Enter user details
# Enter complex pass phrase
```

- List public keys  
`gpg --list-public-keys`

- List private keys  
`gpg --list-secret-keys`

- Encrypt a file  
```terminal
gpg --encrypt --output encryptedfilename.gpg --recipient someemail@email.net filenametoencrypt
```

- Decrypt a file  
```terminal
gpg --decrypt --output decryptedfilename.txt encryptedfilename.gpg

# Enter private key pass phrase
```





---
Reference(s): 