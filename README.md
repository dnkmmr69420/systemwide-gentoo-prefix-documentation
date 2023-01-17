# systemwide gentoo prefix installation documentation

Here is some documentation to install gentoo prefix for all users

1. create a new user by typing this 

```bash
sudo useradd -m -d /var/gentoo gentoo
```

2. Make the user folder readable and executable for all users

```bash
sudo chmod -R a+rx /var/gentoo
```

3. set a password for the user gentoo. if user is not detected open up a new tab on the terminal

```bash
sudo passwd gentoo
```
## logging into the user gentoo

4. now log out and log into the user gentoo with the password that you have set up on step 3

5. now follow the steps on this [page](https://wiki.gentoo.org/wiki/Project:Prefix/Bootstrap)