# Virglrenderer angle-vulkan for android aarch64 termux.

## Install:
```
cd && pkg install wget virglrenderer angle-android
wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/vgl && chmod +x ~/vgl
```
## Usage:
Make sure to kill the current running process of virgl_test_* before launching your app like so:
```
~/vgl q
```
and then simply
```
~/vgl firefox
```
or
```
~/vgl your_termux_x11_binary_app
```

# Using angle-android (built 2024.12.13):

## Install:
```
cd && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24533/angle-android_2.1.24533_aarch64.deb
dpkg -i angle-android_2.1.24533_aarch64.deb
```
and then repeat usage above.

# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android
