# Making virgl setup easier and simpler on termux.
### Install dependecies:
```
pkg install wget virglrenderer-android virglrenderer angle-android openssl which
```

### Install vgl
```
cd && rm -rf ~/vgl && wget https://github.com/ar37-rs/virgl-angle/raw/refs/heads/main/vgl && chmod +x ~/vgl
```

# Usage (on desktop environment native termux-x11):
[(Read for more info to setup xfce4 desktop for native termux-x11)](https://github.com/ar37-rs/xfce4-termux)

Make sure to set config before launching your app like so:
```
~/vgl use-angle
```
or use virgl android (fix for some gpus unable to use angle-vulkan issue)
```
~/vgl use-android
```
and then simply
```
~/vgl firefox
```
or
```
~/vgl any_termux_x11_binary_app
```

# Additional usage:
Using different version of OpenGL COMPAT

(default is 4.1COMPAT)

support profile OpenGL 2.1, 3.2, 3.3, 4.1 and 4.3 with ```COMPAT``` like so
```
vgl 3.3COMPAT
```

Using angle vulkan null display (default)
```
~/vgl angle=vulkan-null
```

Using angle vulkan
```
~/vgl angle=vulkan
```

Using angle gl/es
```
~/vgl angle=gl
```

Terminate running virgl process
```
~/vgl q
```

Update angle-android with the latest build (for android 9+ only)
```
~/vgl update-angle
```

# Usage for wine:
Fix virglrenderer-v1.x.x such incorrect color on d3d

(Direct X) apps/games use d3d config like so:
```
~/vgl cfg=d3d
```
and then
```
~/vgl wine any_d3d_games
```
or

[(Read for more info on how install and run wine using xow64_wine + virgl)](https://github.com/ar37-rs/xow64-wine)

to switch back using OpenGL config use command,
```
~/vgl cfg=gl
```

for OpenGL apps/games on wine use OpenGL config as above.

# Note:
#### Fix vulkan support for some devices

[such encountered on this issue](https://github.com/ar37-rs/virgl-angle/issues/1)
```
pkg remove *icd-swrast && pkg install vulkan-loader-generic wget openssl && cd && rm -rf ~/mesa-vulkan-icd-wrapper_25.0.0-1_aarch64.deb && wget https://github.com/ar37-rs/virgl-angle/releases/download/latest/mesa-vulkan-icd-wrapper_25.0.0-1_aarch64.deb && dpkg -i ~/mesa-vulkan-icd-wrapper_25.0.0-1_aarch64.deb
```

#### Using angle-android latest prebuilt

with vulkan validation layer (13.9 MB+, android 9+ only):
```
~/vgl update-angle
```
or
```
cd && rm -rf ~/angle-android_2.1.2-latest.deb && wget https://github.com/ar37-rs/virgl-angle/releases/download/latest/angle-android_2.1.2-latest.deb
dpkg -i ~/angle-android_2.1.2-latest.deb
```

#### Using virglrenderer-1.1.0 or newer build (stable, android 9+ only):

(recommended for stability)
```
~/vgl update-renderer
```
or
```
cd && rm -rf ~/virglrenderer-1.1.0-latest_aarch64.deb && wget https://github.com/ar37-rs/virgl-angle/releases/download/latest/virglrenderer_1.1.0-latest_aarch64.deb
dpkg -i ~/virglrenderer_1.1.0-latest_aarch64.deb
```
# Usage on proot-distro:
Copy vgl file like so:
```
cp /data/data/com.termux/files/home/vgl /usr/bin/vgl && chmod +x /usr/bin/vgl
```

and then repeat usage above as needed.

# Source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android

# Thanks to:
[Termux Team and Maintainers]( https://github.com/termux) and many other contributors for making termux things happen.

