# systemwide gentoo prefix installation documentation

Warning: this may not be 100% secure but you need root privleges to install packages into that directory. Suggest me ways to make this more secure if you can.

Here is some documentation to install gentoo prefix for all users

1. create a new user by typing this 

```bash
sudo useradd -m -d /var/lib/gentoo gentoo
```


2. set a password for the user gentoo. if user is not detected open up a new tab on the terminal

```bash
sudo passwd gentoo
```
## logging into the user gentoo

3. now log out and log into the user gentoo with the password that you have set up on step 3

4. now follow the steps on this [page](https://wiki.gentoo.org/wiki/Project:Prefix/Bootstrap)

Note: if gentoo fails to install, create an arch linux container by typing the following. doing this will require [distrobox](https://github.com/89luca89/distrobox) to be installed

## create an arch linux container

```bash
distrobox create -i archlinux:latest -n arch -p
```

 install base-devel by typing this
 
 ```bash
 sudo pacman -S base-devel
 ```
 
 go to step 4
 
 ## post installation
 
 5. make /var/lib/gentoo readable and executable by all users. Note: /var/lib/gentoo still stays read only for all users except root (able to do anything regardless of permissions) and the gentoo user
 
 ```bash
 sudo chmod -R a+rx /var/lib/gentoo
 ```
 

 
 ## Usage
 
 Avoid running emerge as root. To enter as the gentoo user, run this
 
 ```bash
 su gentoo
 ```
 
 it should ask for your password. After it asks for your password, you should be running as that user in the terminal.
 
 ## Some optional extra steps
 
 6. hide gentoo user from login screen. ake sure the user isn't running.
 
 ```bash
 sudo usermod -u 980 gentoo
 ```
 
 7. symlink emerge to ~/.local/bin for easier acess (while in the gentoo user)

```bash
ln -s ~/gentoo/usr/bin/emerge ~/.local/bin
```

if the bin folder doesn't exist type

```bash
mkdir ~/.local/bin
```
 
 ## uninstallation
 
 Delete the gentoo directory
 
 ```bash
 sudo rm -r /var/lib/gentoo
 ```
 
 delete the gentoo user
 
 ```bash
 sudo userdel gentoo
 ```
