
# Commonly used commands 

## Ubuntu listing missing drivers for devices

```
sudo ubuntu-drivers devices
```

## Check hyperthreading state of all processors

```
{ sudo echo 0 1; for i in $(seq 1 $(echo $(nproc --all) -1 | bc )); do echo $i $(sudo cat /sys/devices/system/cpu/cpu$i/online) ; done } | less;
```

## Enable disable HT for particular core

```
ht_on() {
  sudo bash -c "echo 1 > /sys/devices/system/cpu/cpu$1/online" 
}
# echo 0 for disabling
```