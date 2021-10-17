# My custom maps

## Maps currently included:

`assembly:/_pro/scenes/users/notex/test.entity`

`assembly:/_pro/scenes/users/notex/blank_slate.entity`

https://user-images.githubusercontent.com/43296291/137613872-cef80d17-fe20-416f-8322-0cbba06c7a7b.mp4

---

> OUTDATED INSTRUCTIONS (WAIT FOR MOD FRAMEWORK)

## Instructions for use

### Compiling the map

1. Clone this repo to your computer
2. Download the latest version of the RPKG Tool from [https://notex.app/rpkg/](https://notex.app/rpkg/)
3. Download the latest version of ResourceTool from [https://github.com/OrfeasZ/ZHMTools/](https://github.com/OrfeasZ/ZHMTools/)
4. Download the latest version of QuickEntity from [https://rentry.co/QuickEntityDocs/](https://rentry.co/QuickEntityDocs/)
5. Make sure rpkg-cli.exe and ResourceTool.exe are in your PATH environment variable or in the QuickEntity folder.
6. Use QuickEntity's `QuickEntity JSON to TEMP/TBLU` feature (Saving the output files into the chunk28 folder located in packaging)
7. Run generate_rpkg.bat (You may want to edit the destination folder in the last line of this script)

### Launching the map

1. Drag your game's packagedefintion.txt file (Located in the game's Runtime folder) into [https://www.notex.app/tools/online/xtea](https://www.notex.app/tools/online/xtea)
2. Add the following to the end of your packagedefintion file (Rename **test.entity** depending on which map you are using):

```
// --- Chunk 28 Notex
@partition name=notex parent=season3 type=standard patchlevel=2
// --- notex.packagedefinition
[assembly:/_pro/scenes/users/notex/test.entity].entitytemplate
```

3. Click save file and copy the new packagedefintion.txt to your game, replacing the old one.
4. Drag thumbs.dat (From the game's Retail folder) into the XTEA site and replace the `BENCHMARK_` lines with the following: (Making sure to remove `BENCHMARK_SCENE_01_SIMQUALITY_01`, otherwise the game will load a brick for another level)

```
BENCHMARK_SCENE_01=assembly:/_pro/scenes/users/notex/test.entity
BENCHMARK_SCENE_01_MODE=1
```

5. Launch the game with the following command line argument `-ao START_BENCHMARK true -ao BENCHMARK_SCENE_INDEX 1 ConsoleCmd UI_ShowProfileData 0 -SKIP_LAUNCHER` and it should now load straight into this map.
6. Alternatively you can edit `SCENE_FILE=` instead but the game will always boot into the custom map by default then.
