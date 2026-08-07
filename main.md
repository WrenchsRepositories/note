# ***CONTENTS***
- [CONTENTS](#contents)
- [MAC](#mac)
  - [Homebrew](#homebrew)
  - [MacOS command](#macos-command)
- [LINUX](#linux)
  - [Linux command](#linux-command)
- [RASPBERRYPI](#raspberrypi)
  - [Connect](#connect)
- [TOOLS](#tools)
  - [git](#git)
  - [ssh](#ssh)

# ***MAC*** 

## ***Homebrew***

### Install homebrew China node mirror
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

## ***MacOS command***

### Restart DNS
```shell
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
```


# LINUX

## ***Linux command***

### Add shellscript alias to .bashrc
1.	Edit .shellrc
2.	Add `scriptname() {[space]bash[space]"${SCRIPT_PATH}"[space]"$@";[space]}`
3.	Run source ~/.bashrc

## ***Linux tools***
1. `btop`
2. `jq`
3. `exa`
4. `lolcat`(toys)
5. `cmatrix`(toys)


# ***RASPBERRYPI***

## ***Connect***

### Using mDNS ssh raspberrypi
1.	Edit /boot/firmware/cmdline.txt
	and add `modules-load=dwc2,g_ether` after "rootwait"

2.	Edit /boot/firmware/config.txt
	down to [all] 
	add `dtoverlay=dwc2`

3.	Create a new file named "ssh" in the /boot folder
	SSH raspberrypi's hostname.local


# ***TOOLS***

## ***git***

### Change editor
```shell
git config --global core.editor "vim"
```
### Log only show your own commit
```shell
git log --author="$(git config user.name)" --pretty=oneline
```
### Add git lola
```shell
git config --global alias.lola "log --graph --decorate --oneline --all" 
```

## ***ssh***

### Key 
```shell
ssh-keygen -t ed25519 -C "description"
```

### Remote host identification has changed
```shell
ssh-keygen -R IP
```

[back to Contents](#Contents)
