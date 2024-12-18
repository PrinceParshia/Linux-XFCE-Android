## ARCH XFCE
![1000250622](https://github.com/user-attachments/assets/0ffde6ca-8eff-4337-aae5-73ed36704026)
![1000250623](https://github.com/user-attachments/assets/f1aa1f82-c743-47fe-b0d9-7a1e0a4bcf65)

---
#### NOTE
* ~ $ is Termux Shell.
* [root@localhost ~]# is Arch Shell.
---
## MAIN STEPS
Open Termux and install required packages:
```
pkg update && pkg upgrade
pkg install x11-repo
pkg install termux-x11 proot-distro pulseaudio wget
```
Install Arch:
```
proot-distro install archlinux
proot-distro login archlinux
```
In Arch Shell update its packages:
```
pacman -Syu
```
Install xfce4 and additional packages:
```
pacman -S xfce4 xfce4-goodies tumbler engrampa ristretto parole sudo git
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
To save and exit press CTRL - X - Y - ENTER.
<br>
Arch linux dont have their own/default xfce theme. So i suggest a theme to use instead of the default xfce theme(optional):
<br>
Install the theme and other required packages:
```
pacman -S arc-gtk-theme papirus-icon-theme git
```
Install the xfce configurations:
```
git clone https://github.com/Anemosfy/Arch-Linux-XFCE-Customization.git
```
Apply the configurations:
```
rm -r /home/<username>/.config/xfce4
```
```
cp -r /root/Arch-Linux-XFCE-Customization/.config/xfce4 /home/<username>/.config/
```
```
cp /root/Arch-Linux-XFCE-Customization/whiskermenu-archlinux.png /usr/share/icons/
```
---
## INSTALL DEBUG METHOD (TERMUX-X11)
Execute ```exit``` until you appear in Termux Shell.
Download the Arch Startup file:
```
wget https://raw.githubusercontent.com/Anemosfy/Termux-X11-Linux-DEs/refs/heads/main/arch/arch-xfce.sh
```
```
nano arch-xfce.sh
```
Scroll to line 10 and change ```<username>``` to your username you created in Arch Shell. CTRL - X - Y - ENTER.
```
chmod +x arch-xfce.sh
```
Start Arch desktop with: 
```
./arch-xfce.sh
```
---
## TO DO AFTER INSTALLATION (CHROMIUM)
After Arch is launched:
<br>
If you use chromium do this step:

![1000250626](https://github.com/user-attachments/assets/b98f63ca-a829-456d-a7c0-32162e371cb4)
Add the ```--no-sandbox``` flag:
![1000250627](https://github.com/user-attachments/assets/2d45364f-4be0-4e72-9d6f-c5e488d89703)
All done!

---
## TOOLTIP
* Start X11 connection using (In Termux Shell):
  ```
  ./arch-xfce.sh
  ```
  And vnc connection using (In Termux Shell):
  ```
  ./arch-xfce-vnc.sh
  ```
* Close X11 connection using the exit button on the notifications bar. And vnc connection using (in arch shell):
  ```
  vncserver -kill :1 
  ```
* Open Arch Shell in Termux using:
  ```
  proot-distro login archlinux
  ```
  And with a specific user:
  ```
  proot-distro login archlinux --user <username>
  ```
