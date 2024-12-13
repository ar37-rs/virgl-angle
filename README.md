# Virglrenderer angle-vulkan for android aarch64 termux.

## Install:
```
cd && pkg install tar wget virglrenderer angle-android
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
cd && pkg install tar wget virglrenderer
wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24521/angle-android_2.1.24521-aarch64.tar.xz
tar -xvf angle-android_2.1.24521-aarch64.tar.xz && chmod +x ~/cli/vgl
```
## Usage:
Make sure to kill the current running process of virgl_test_* before launching your app like so:
```
~/cli/vgl q
```
and then simply
```
~/cli/vgl firefox
```
or
```
~/cli/vgl your_termux_x11_binary_app
```
# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android
