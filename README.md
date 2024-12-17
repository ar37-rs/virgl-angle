# Virglrenderer angle-vulkan for android aarch64 termux.
Install:
```
cd && pkg install wget virglrenderer angle-android
rm -rf ~/vgl && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/vgl && chmod +x ~/vgl
```
## Usage:
Make sure to kill the current running process of virgl_test_* and use EGL angle before launching your app like so:for d3d (Direct 3D) apps/games on wine 
```
~/vgl use-egl
```
and then simply
```
~/vgl firefox
```
or
```
~/vgl your_termux_x11_binary_app
```

# Usage on wine:
To fix virglrenderer-v1.x.x incorrect color (too dark) on d3d
(Direct X) apps/games use d3d config like so:
```
~/vgl use-d3d
```

# Usage on proot-distro:
Copy vgl file like so:
```
cp /data/data/com.termux/files/home/vgl /usr/bin/vgl && chmod +x /usr/bin/vgl
```

# Using angle-android (built 2024.12.13):
Install:
```
cd && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24533/angle-android_2.1.24533_aarch64.deb
dpkg -i angle-android_2.1.24533_aarch64.deb
```
and then repeat usage above.

# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android
