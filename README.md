# Virglrenderer angle-vulkan for android aarch64 termux.

## Install:
```
cd && pkg install wget virglrenderer angle-android
wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24521/vglx && chmod +x ~/vglx
```
## Usage:
Make sure to kill the current running process of virgl_test_* before launching your app like so:
```
~/vglx q
```
and then simply
```
~/vglx firefox
```
or
```
~/vglx your_termux_x11_binary_app
```

# Using angle (built 2024.12.12):

## Install:
```
cd && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24521/angle-android_2.1.24521_aarch64.deb
dpkg -i angle-android_2.1.24521_aarch64.deb
```
and then repeat usage above.

# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android
