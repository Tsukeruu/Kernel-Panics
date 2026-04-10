# Kernel-Panics
- What exactly is a kernel panic? It's a type of kernel error where the system enters a fatal state in which it cannot continue without any dataloss, such cases are severe and require booting from the usb to fix the system

# The situation
- I was updating my arch linux setup via sudo pacman -Syu and mid update, my wifi cut off for 2 seconds, I thought it was normal since usually the installation pauses, but what I did not know was it was updating gcclibs which is a crucial package for all linux environments, after realizing it was gone my system entirely stopped working and i researched on my phone on what to do next, it said to not reboot or it may be fatal, however the only fix i had was to boot into the live usb which is the same usb that i've dualbooted my windows and linux together.

# My solution
- Of course after booting into the usb I was greeted with the live shell, my pacman wasnt working so I needed to connect to my internet via iwctl. After connecting successfully i needed to install gcclibs via pacstrap which is the same as pacman but for initializing new linux systems, so it comes with the defaults and essentials. I first mounted my main partition and ran pacstrap -K gcc-libs, where it installs successfuly, after thinking this was my solution, I unmount my main partition via umount -R and then rebooted. After rebooting i was greeted with my grub bootloader and i chose my linux environment, 20 seconds in and i was greeted with a kernel panic
- [img]()
