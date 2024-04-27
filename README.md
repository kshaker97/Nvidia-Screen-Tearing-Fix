# Nvidia Screen Tearing Fix
Solving nvidia legacy graphics cards screen tearing issue on linux based operating systems.

## Steps
1. Create file named /etc/modprobe.d/99-prime-sync.conf
```
 sudo touch /etc/modprobe.d/99-prime-sync.conf
```
2. Put inside it options nvidia-drm modeset=1
```
 sudo echo "options nvidia-drm modeset=1" > /etc/modprobe.d/99-prime-sync.conf
```
3. Update initramfs
```
 sudo update-initramfs -u
```
4. Check the module option is active
```
 sudo cat /sys/module/nvidia_drm/parameters/modeset 
```
