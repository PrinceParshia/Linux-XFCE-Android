## MANJARO-XFCE
![Screenshot_2024-11-21_08-03-21](https://github.com/user-attachments/assets/762326c2-71d5-4dd9-9a12-a056a02fcd66)

---
Info: (~ $) is Termux Shell, ([root@localhost ~]#) is Manjaro Shell. Don't miss any commands!

Open Termux and install required packages:
```
pkg update && pkg upgrade
pkg install x11-repo
pkg install termux-x11 proot-distro pulseaudio wget
```
Install Manjaro:
```
proot-distro install manjaro
proot-distro login manjaro
```
In Manjaro Shell update its packages:
```
pacman -Syu
```
Fix a problem:
```
nano /etc/pacman.conf
```
Scroll and change SigLevel value to Never:
```
SigLevel = Never
```
To save and exit press CTRL - X - Y - ENTER.

Install xfce4 and additional packages:
```
pacman -S xfce4 xfce4-goodies tumbler engrampa git sudo
```
Install a browser to access internet:
```
pacman -S chromium
```
```
pacman -S firefox
```
Make an user to access the desktop:
```
useradd -m <username>
```
Set a password for your user:
```
passwd <username>
```
Give sudo access to your user:
```
nano /etc/sudoers
```
Scroll and paste it under (root ALL=(ALL:ALL) ALL):
```
<username> ALL=(ALL:ALL) ALL
```
CTRL - X - Y - ENTER.

Login to your user:
```
su - <username>
```
Install Manjaro default xfce theme:
```
git clone https://gitlab.manjaro.org/profiles-and-settings/manjaro-xfce-settings.git
```
```
mv manjaro-xfce-settings/skel/.config /home/<username>/
```
Execute ```exit``` until you appear in Termux Shell.

Download the Manjaro Startup file:
```
wget https://raw.githubusercontent.com/Anemosfy/Linux-XFCE-Android/refs/heads/main/manjaro/manjaro-xfce.sh
```
```
nano manjaro-xfce.sh
```
Scroll to line 20 and change ```<username>``` to your username you created in Manjaro Shell. CTRL - X - Y - ENTER.
```
chmod +x manjaro-xfce.sh
```
Start Manjaro desktop with: 
```
./manjaro-xfce.sh
```
Open Edit Application window of Chromium and add ```--no-sandbox``` after the command.
Open Chromium and Download [Matcha-Sea](https://www.xfce-look.org/p/1187179/ ),[Papirus-Teal-Folders](https://www.xfce-look.org/p/1166289/). Then execute:
```
cd Downloads/
```
Adjust names:
```
tar -xf Matcha*.tar.xz
```
```
tar -xf Papirus*.tar.xz
```
Choose a Matcha version you want(Dark/light/default-mixed):
```
mv Matcha-version /usr/share/themes/
```
```
mv Papirus /usr/share/icons/
```
Choose Papirus dark or light version:
```
mv Papirus-version /usr/share/icons/
```
```
cd /usr/share/icons/
```
```
git clone https://raw.githubusercontent.com/anemosfy/Linux-XFCE-Android/refs/heads/main/manjaro/manjaro-xfce.sh
```
Change the default theme from Settings -> Appearance. Add the Manjaro icon on panel from Panel Preferences -> Items -> Whisker Menu Settings -> Appearance, Select icon from /usr/share/icons/manjaro-icons/maia/128x128.png.
## TOOLTIP
* Start Manjaro Desktop using (In Termux Shell):
  ```
  ./manjaro-xfce.sh
  ```
* Close Manjaro Desktop using the exit button on the notifications bar
* Open Manjaro Shell in Termux using:
  ```
  proot-distro login manjaro
  ```
  And with a specific user:
  ```
  proot-distro login manjaro --user <username>
  ```
