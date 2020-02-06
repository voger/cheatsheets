### Create a windows bootable usb from cd or img

```console
sudo woeusb --device Windows7_x64.iso /dev/sdX
sudo woeusb --device /dev/sr0 /dev/sdX
```

### Write a linux image to usb

```console
sudo dd of=/dev/sdc if=manjaro-xfce-18.0.4-x32-stable-minimal-i686.iso bs=4096
```

Or use etcher
