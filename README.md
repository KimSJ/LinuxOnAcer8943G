LinuxOnAcer8943G
================

Notes on stuff I did to my lappy to make Ubuntu 12.10 work
---

[Get the Internal SD Card Reader working on Acer 8943G](http://www.edmondscommerce.co.uk/ubuntu/get-the-internal-sd-card-reader-working-on-acer-8943g-probably-plus-others-ubuntu-10-10/)
```
cd /etc/modprobe.d
sudo nano sdcardread.conf
```
Add
```
options sdhci debug_quirks=0x40
```
save and quit nano
```
sudo rmmod sdhci_pci
sudo rmmod sdhci
sudo modprobe sdhci
sudo modprobe sdhci_pci

sudo update-initramfs -u
```
(Not sure if that last command is actually needed; didn't try reboot before I executed it)

[Add Open Command Prompt Here Functionality To Nautilus:](http://www.watchingthenet.com/add-open-command-prompt-here-functionality-to-nautilus-in-ubuntu.html)
```
sudo apt-get install nautilus-open-terminal
killall nautilus
```
