# Setup: Install Software on Ubuntu

Collection of steps for installing programs on Ubuntu.

## KeepassXC

[KeePassXC Download Linux](https://keepassxc.org/download/#linux)

[Another KeePassXC install link](https://omgfoss.com/install-keepassxc-password-manager-ubuntu-18-04-lts/)

**How To Install KeePassXC Password Manager On Ubuntu 18.04 LTS**

You need to add the PPA of KeePassXC before proceeding for installation. Now, You need to run the following commands to install KeePassXC Password Manager on Ubuntu Systems:

```
sudo add-apt-repository ppa:phoerious/keepassxc
sudo apt-get update
sudo apt-get install keepassxc
```

**Run from terminal**

```
keepassxc
```

## Sublime Text

[Linux Package Manager Repositories apt](https://www.sublimetext.com/docs/linux_repositories.html#apt)

**Linux Package Manager Repositories**

Sublime Text includes an auto-upgrade mechanism on Windows and Mac to make upgrades a snap. Instead of going against the grain of the Linux ecosystem, packages and package repositories are provided for most of the major distributions. 

**Builds listed in the dev channel are only available to licensed users. Users who are evaluating Sublime Text before purchase will need to use the stable channel.**

**apt** 

The apt repository contains packages for both x86-64 and arm64. Install the GPG key: 

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

Ensure apt is set up to work with https sources: 

```
sudo apt-get install apt-transport-https
```

Select the channel to use: 
	
Stable

```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
	
Dev

```
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

Update apt sources and install Sublime Text 

```
sudo apt-get update
sudo apt-get install sublime-text
```

**Run From Terminal**

```
subl
```

## Zim - A Desktop Wiki

[Zim - A Desktop Wiki](https://zim-wiki.org/)

```
sudo add-apt-repository ppa:jaap.karssenberg/zim
sudo apt-get update

sudo apt-get install zim
```

Check version

```
zim -v
```


## cherrytree - A hierarchical note taking application

[cherrytree - A hierarchical note taking application](https://www.giuspen.com/cherrytree/)

CherryTree is available with the base repositories of Ubuntu. You can install it using the following command or directly by clicking the below button:

```
sudo apt-get install cherrytree
```

Note that the CherryTree Text Editor available with the Ubuntu base repositories are outdated. If you need the latest version of CherryTree, you can install it by downloading the deb file from the Official Website or install it by adding PPA.

Install using PPA:

The main benefit of installing CherryTree by adding PPA is to get automatic updates of CherryTree using systems software updater.

```
sudo add-apt-repository ppa:giuspen/ppa
sudo apt-get update
sudo apt-get install cherrytree
```

## VirtualBox

You can also install it from the command line using this command:

```
sudo apt-get update
sudo apt install virtualbox
```

However, if you check the package version before installing it, you’ll see that the VirtualBox provided by Ubuntu’s repository is quite old.

For example, the current VirtualBox version at the time of writing is 6.0, but the one in Software Center is 5.2. This means you won’t get the newer features introduced in the latest version of VirtualBox.

**Run from terminal**

```
virtualbox
```