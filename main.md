# CONTENTS
- [CONTENTS](#contents)
- [MAC](#mac)
  - [Install homebrew China node mirror](#install-homebrew-china-node-mirror)
  - [Restart DNS](#restart-dns)
- [LINUX](#linux)
  - [Linux command](#linux-command)
    - [Add shellscript alias to .bashrc](#add-shellscript-alias-to-bashrc)
- [RASPBERRYPI](#raspberrypi)
  - [Using mDNS ssh raspberrypi](#using-mdns-ssh-raspberrypi)
- [TOOLS](#tools)
  - [git](#git)
    - [Log only show your own commit](#log-only-show-your-own-commit)
    - [Add git lola](#add-git-lola)
  - [ssh](#ssh)
    - [Key](#key)
    - [Remote host identification has changed](#remote-host-identification-has-changed)

# MAC 

## Install homebrew China node mirror
1. Add to .shellrc
```shell
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"
export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.ustc.edu.cn/homebrew-bottles"
export HOMEBREW_API_DOMAIN="https://mirrors.ustc.edu.cn/homebrew-bottles/api"
```
2.
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Restart DNS
```shell
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
```


# LINUX

## Linux command

### Add shellscript alias to .bashrc
1.	Edit .shellrc
2.	Add `scriptname() {[space]bash[space]"${SCRIPT_PATH}"[space]"$@";[space]}`
3.	Run source ~/.bashrc


# RASPBERRYPI 

## Using mDNS ssh raspberrypi
1.	Edit /boot/firmware/cmdline.txt
	and add `modules-load=dwc2,g_ether` after "rootwait"

2.	Edit /boot/firmware/config.txt
	down to [all] 
	add `dtoverlay=dwc2`

3.	Create a new file named "ssh" in the /boot folder
	SSH raspberrypi's hostname.local


# TOOLS

## git

### Log only show your own commit
```shell
git log --author="$(git config user.name)" --pretty=oneline
```
### Add git lola
```shell
git config --global alias.lola "log --graph --decorate --oneline --all" 
```

## ssh 

### Key 
```shell
ssh-keygen -t ed25519 -C "description"
```

### Remote host identification has changed
```shell
ssh-keygen -R IP
```

[back to Contents](#Contents)
