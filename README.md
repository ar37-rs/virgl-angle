# Making virgl setup easier and simpler on termux.
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

or use virgl android (fix for some gpus unable to use angle-vulkan issue)
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
If there's some color issues (if not, skip this), to fix virglrenderer-v1.x.x such incorrect color (or too dark) on d3d
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

# Using angle-android (2024.12.27) fix for vulkan crashing on some android 8+
prebuilt vulkan with validation layer (fast and more stable) 13.9 MB:
```
cd && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24570/angle-android_2.1.24570_aarch64.deb
dpkg -i angle-android_2.1.24570_aarch64.deb
```
or minimal version (for android 7+) without vulkan validation layer 2.9 MB (slower):
```
cd && wget https://github.com/ar37-rs/virgl-angle-termux/releases/download/2.1.24570/angle-android_2.1.24570_aarch64.deb
dpkg -i angle-android_2.1.24570_minimal.deb
```

and then repeat usage above.

# source code building angle-android from termux official:
https://github.com/termux/termux-packages/tree/master/packages/angle-android
