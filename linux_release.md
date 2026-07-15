# CONTENTS
- [ARCH](#arch)

# ARCH

## Wireless WIFI connect
```shell
iwctl 
device list 
station wlan0 scan 
station wlan0 get-networks
station wlan0 connect wifi-name 
exit 
```

## Sync system time
```shell
timedatectl set-ntp true
timedatectl status
```