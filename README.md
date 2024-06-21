<p align="center"><img alt="Left 4 Dead Launcher" src="launcher/icon.png"/></p>
<h1 align="center">Left 4 Dead Launcher</h1>

<!--
![Left 4 Dead Launcher](launcher/icon.png)

Left 4 Dead Launcher
====================
-->

Launcher for Valve’s [Left 4 Dead 2](https://store.steampowered.com/app/550) is a nice GUI that allows to start the game with different set of addons and enforce the addon order by making `addonlist.txt` read-only.

![Left 4 Dead Launcher](launcher/screenshot.webp "Left 4 Dead Launcher")

The intention here is to easily allow launching the game in its normal state or in [original Left 4 Dead](https://store.steampowered.com/app/500) mode, which is useful when playing the ported Left 4 Dead 1 campaigns and other content featuring the original survivors. Technically, what it does is toggling a pre-configured set of addons, which either brings some of the original dark & moody Left 4 Dead 1 atmosphere or switches things back to the more light-hearted Left 4 Dead 2 feeling, – all with a single button press in the launcher. Stuff that can be changed: menu icons with L4D1 cast, original menu font, hud, textures, models, etc., – anything that can be modified using game’s addon system.

Left 4 Dead launcher is built as a [Microsoft HTML Application](https://learn.microsoft.com/en-us/previous-versions/ms536496(v=vs.85)) (HTA), which means it is open by nature, very lightweight, and doesn’t depend on a huge runtime.

How to Use
----------

  * Download the [core VPKs](https://drive.google.com/drive/folders/19-pyWdOulIBfPqkBIr8szpqkNown9Ni3?usp=drive_link) and extract them to `Steam\steamapps\common\Left 4 Dead 2`. You will end up with two more folders in game directory: `left4dead1` and `fontscheme`. The `left4dead1` folder contains VPKs that get activated when launching the game in Left 4 Dead 1 mode: they include the original font and loading screen graphics. The `fontscheme` has the Left 4 Dead 2 font instead. (You can also find the core VPKs on the [release page](https://github.com/ubihazard/l4d-launcher/releases/tag/1.0).)

  * Download Left 4 Dead 1 menu screen [cinematics](https://github.com/ubihazard/l4d-launcher/releases/download/1.0/Videos.zip) and move them to `Steam\steamapps\common\Left 4 Dead 2\left4dead2\media`. There are also alternative HD backgrounds [available on Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=2490673505). Just make sure to rename the files by putting `.l4d1` after their file name and before the `.bik` file extension, like so: `l4d2_background01.l4d1.bik`. Make sure not to replace any of the original Left 4 Dead 2 cinematic files.

  * You will need some VPK with original L4D1 content. A pre-made Left 4 Dead 1 VPK is [available](https://drive.google.com/file/d/1Q_SMTXo11u4yBOmAJB_7BZtV8qQAchRV/view?usp=drive_link) from the same shared Google Drive folder. Put it inside `Steam\steamapps\common\Left 4 Dead 2\left4dead2\addons` and add it to the list of VPKs to [activate](https://github.com/ubihazard/l4d-launcher#configuring-the-launcher) in `launcher.cfg`: `l4d1.vpk 1`. Of course you can make your own VPKs if you know how to mod the game.

  * Download the [latest L4D launcher release](https://github.com/ubihazard/l4d-launcher/releases) and extract the launcher files to `Steam\steamapps\common\Left 4 Dead 2`, where `left4dead2.exe` is located. Double-click the `launcher.hta` to reveal its GUI.

L4D launcher works with Valve’s [Steam](https://store.steampowered.com/about/), which has to be installed on your system. The game will be launched through Steam and will inherit all launch options you’ve got configured in Steam properties for Left 4 Dead 2.

Configuring the Launcher
------------------------

`launcher.cfg` contains the list of VPKs to activate or de-activate when launching the game. To activate a particular VPK when launching as Left 4 Dead 1, add it with `1` after its name (just like `addonlist.txt`); to activate it when launching Left 4 Dead 2, add it with `0` instead. A VPK that is enabled in L4D1 will be disabled in L4D2, and vice versa.

An example of a well-formatted `launcher.cfg`:

```ini
make_addonlist_read_only=no
l4d1_addon_vpks=
l4d1.vpk 1
scar-l.vpk 0
m4a4.vpk 1
```

In order for `launcher.cfg` to appear, L4D launcher has to be run at least once. Set `make_addonlist_read_only` to `yes` if you need to enforce addon loading order.

Additional VPKs
---------------

The `addons` subfolder inside the [shared folder](https://drive.google.com/drive/folders/19-pyWdOulIBfPqkBIr8szpqkNown9Ni3?usp=drive_link) contains several addon packs assembled from publicly available sources with lots of bug fixes and various enhancements, staying as close as possible to vanilla experience. Many of the included addons were modified by me. Some `.vtf` textures were touched up using my [lossless DXT VTF tools](https://github.com/ubihazard/vtf-tools).

The `modding` subfolder has most of the source files for every piece of content which I had to create, patch, or modify in some way: models, animations, textures, etc.

⭐ Support
---------

If you like [Left 4 Dead launcher](https://github.com/ubihazard/l4d-launcher) you can [buy me a ☕](https://www.buymeacoffee.com/ubihazard "Donate")!
