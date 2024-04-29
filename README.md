<h1 align="center">
  Nvidia Screen Tearing Fix
</h1>

<h4 align="center">Solving nvidia legacy graphics cards screen tearing issue on linux based operating systems.</h4>

## Steps
1. **Create a File /etc/modprobe.d/99-prime-sync.conf:**
```
 sudo touch /etc/modprobe.d/99-prime-sync.conf
```
2. **Add this Module Option 'options nvidia-drm modeset=1' to the File:**
```
 sudo echo "options nvidia-drm modeset=1" > /etc/modprobe.d/99-prime-sync.conf
```
3. **Update initramfs:**
```
 sudo update-initramfs -u
```
4. **Reboot:**
```
 sudo systemctl reboot
```
6. **After Reboot Check Whether the Module Option is Active:** 
```
 sudo cat /sys/module/nvidia_drm/parameters/modeset 
```
