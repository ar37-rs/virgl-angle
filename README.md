# Making virgl setup easier and simpler on termux.
Install dependecies:
```
pkg install wget virglrenderer-android virglrenderer angle-android openssl
```

Install vgl
```
cd && rm -rf ~/vgl && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/vgl && chmod +x ~/vgl
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

Update angle-android with the latest build
```
~/vgl update-angle
```

# Usage on wine:
If there's some color issues (if not, skip this), to fix virglrenderer-v1.x.x such incorrect color (or too dark) on d3d
(Direct X) apps/games use d3d config like so:
```
~/vgl config=d3d
```
and then
```
~/vgl wine any_d3d_games
```
or

[(Read for more info on how install and run wine using xow64_wine + virgl)](https://github.com/ar37-rs/xow64-wine)

to switch back using OpenGL config use command,
```
~/vgl config=gl
```

# Note:
for OpenGL apps/games on wine use OpenGL config as above.

# Usage on proot-distro:
Copy vgl file like so:
```
cp /data/data/com.termux/files/home/vgl /usr/bin/vgl && chmod +x /usr/bin/vgl
```

# Using angle-android latest build fix for vulkan crashing on some android 8+
prebuilt vulkan with validation layer (more stable) 13.9 MB:
```
cd && rm -rf ~/angle-android_2.1.2-latest.deb && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/angle-android_2.1.2-latest.deb
dpkg -i ~/angle-android_2.1.2-latest.deb
```
or minimal version (for android 7+) without vulkan validation layer 2.9 MB:
```
cd && rm -rf ~/angle-android_2.1.24570_minimal.deb && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/angle-android_2.1.24570_minimal.deb
dpkg -i ~/angle-android_2.1.24570_minimal.deb
```

# Using virglrenderer-1.1.0 newer build (stable, android 10+ only)
(recommended for stability);
```
cd && rm -rf ~/virglrenderer_1.1.0-11_aarch64.deb && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/virglrenderer_1.1.0-11_aarch64.deb
dpkg -i ~/virglrenderer_1.1.0-11_aarch64.deb
```

# Using virglrenderer-1.1.0 with patched direct xcb connection (unstable and not recommended, android 8+ only)
still very buggy (can be used with specific patched mesa virpipe driver):
```
cd && rm -rf ~/virglrenderer_1.1.0-11_aarch64-patched.deb && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/virglrenderer_1.1.0-11_aarch64-patched.deb
dpkg -i ~/virglrenderer_1.1.0-11_aarch64-patched.deb
```

and then repeat usage above.

# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android

# source code building virglrenderer direct connection from termux official:
https://github.com/termux/termux-packages/tree/virglrenderer-direct-x-connection/packages/virglrenderer-android

# Thanks to:
[Twaik Yont](https://github.com/twaik), [Termux Team and Maintainers]( https://github.com/termux) and many other contributors for making termux things happen.

