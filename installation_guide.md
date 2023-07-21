# Installation Guide
This guide will install Hyprland with these dotfiles. \
This guide will assume that you are using a fresh installation of Arch Linux using the "minimal" archinstall profile. \
This guide will not be covering NVIDIA, to get NVIDIA support you'll need to check the Hyprland FAQ to get it working. 

## Quick Tips
You can speed up this process by editing a couple of configuration files. \
We can first edit our `pacman.conf` file to increase the amount of htings we download at once. \
To do this, we can use the following command to open the file in `vim`. (replace `vim` with your editor of choice)
```sh
sudo vim /etc/pacman.conf
```

Once you have this file open, you'll want to look for the following line, and modify the value to your liking.
```conf
ParallelDownloads = 1
```

You also might want to edit your `makepkg.conf` file to decrease the time it takes to compile programs. \
We will be compiling a lot of software in this guide, so I would highly recommend at least doing this. \
To edit the `makepkg.conf` file, we can open it in `vim` with this command. (again, replace `vim` with your editor of choice)
```sh
sudo vim /etc/makepkg.conf
```

Once you have this file open, you'll want to look for the following line, and modify the number to the amount of CPU threads you would like to use when compiling. 
```conf
MAKEFLAGS="-j12"
```

Once these files are setup, compile and download times should be a lot quicker.

## AUR Helper
You'll need an AUR helper in order to follow this guide properly. We'll be using `yay` for this guide. \
For this part of the installation, you'll need to have `git` installed. \
If you don't have `git` installed, you can use the following command to install `git`. 
```sh
sudo pacman -S git
```

To install `yay`, you can use the following commands to install `yay` 

```sh
cd $HOME
git clone https://aur.archlinux.org/yay-git
cd yay-git
makepkg -si
cd ..
rm -rf yay-git

```

Once `yay` is installed, we can start installing the packages we need.

## Installing Hyprland