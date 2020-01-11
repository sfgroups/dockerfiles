grub2-editenv list
grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg

hernet  --

hexdump -C /dev/sda3 |head -40
lsinitrd
--
grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg
--
dracut --regenerate-all -f && grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg

```
# cat grubenv
# GRUB Environment Block
saved_entry=e5743492d59c4e358c120889724f4b8f-4.18.0-80.11.2.el8_0.x86_64
kernelopts=root=/dev/mapper/cl-root ro crashkernel=auto rd.lvm.lv=centos/root rd.lvm.lv=centos/swap net.ifnames=0 biosdevname=0 ipv6.disable=0 audit=1 loglevel=7 systemd.log_level=debug
boot_success=1
boot_indeterminate=0
```

```
# grub2-editenv list
saved_entry=e5743492d59c4e358c120889724f4b8f-4.18.0-80.11.2.el8_0.x86_64
kernelopts=root=/dev/mapper/cl-root ro crashkernel=auto rd.lvm.lv=centos/root rd.lvm.lv=centos/swap net.ifnames=0 biosdevname=0 ipv6.disable=0 audit=1 loglevel=7 systemd.log_level=debug
boot_success=1
boot_indeterminate=0
```
