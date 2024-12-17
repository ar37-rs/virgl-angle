# Virglrenderer angle-vulkan for android aarch64 termux.
Install:
```
cd && pkg install wget virglrenderer-android virglrenderer angle-android
rm -rf ~/vgl && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/latest/vgl && chmod +x ~/vgl
```
## Usage:
Make sure to use EGL angle config before launching your app like so:
```
~/vgl use-egl
```

or use virgl android (fix for adreno gpus unable to use angle-vulkan-null issue)
```
~/vgl use-egl && ~/vgl use-android
```

and then simply
```
~/vgl firefox
```
or
```
~/vgl your_termux_x11_binary_app
```

(Note): to switch back using angle-vulkan use command,
```
~/vgl use-angle
```


# Usage on wine:
To fix virglrenderer-v1.x.x incorrect color (too dark) on d3d
(Direct X) apps/games use d3d config like so:
```
~/vgl use-d3d
```
and then
```
~/vgl wine your_d3d_games
```

note:
for OpenGL apps/games on wine use egl config as above.

# Usage on proot-distro:
Copy vgl file like so:
```
cp /data/data/com.termux/files/home/vgl /usr/bin/vgl && chmod +x /usr/bin/vgl
```

# Using angle-android (built 2024.12.13) optional for testing only:
Install:
```
cd && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24533/angle-android_2.1.24533_aarch64.deb
dpkg -i angle-android_2.1.24533_aarch64.deb
```
and then repeat usage above.

# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android
