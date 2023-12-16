```
wget -O 1.iso https://download.manjaro.org/kde/23.0.4/manjaro-kde-23.0.4-231015-linux65.iso
```
```
wget -O ngrok.tgz https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
```
```
tar -xf ngrok.tgz
```
```
rm -rf ngrok.tgz
```
```
./ngrok config add-authtoken 2ZYa76bRYmYrC7TGlYA5ld5byYa_49eTpsgnWxXmB8LhDR9jo
```
```
./ngrok tcp 5900
```
```
sudo apt update && sudo apt install qemu-kvm -y
```
```
qemu-img create -f raw 1.img 64G
```
```
sudo qemu-system-x86_64 -m 8G -cpu host -boot order=c -drive file=1.iso,media=cdrom -drive file=1.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=2 -device rtl8139,netdev=n0 -netdev user,id=n0 -vga qxl -enable-kvm
```
```
rm -rf 1.iso
```
```
sudo qemu-system-x86_64 -m 8G -cpu host -boot order=c -drive file=1.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=2 -device rtl8139,netdev=n0 -netdev user,id=n0 -vga qxl -enable-kvm
```
