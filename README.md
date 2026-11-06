# BatWiiCeraU

A Wii U menu inspired theme for **Batocera** (EmulationStation theme format 7).
Your systems show up as a 5x3 grid of glassy tiles, like the Wii U home screen, with your
RetroAchievements profile where the Mii would be.

> **Status: experimental.** Built from the Batocera theme documentation and source code, but not yet tested on a
> real device. Expect rough edges and please open an issue with a screenshot if something looks wrong.

## Features
- 5x3 tile grid with a glassy bevel and teal selection border; the selected tile zooms slightly
- Profile tile top-left that downloads **your RetroAchievements picture** and shows your username
  (log in under Game Settings > RetroAchievements; needs internet)
- Icons for most systems from the ES-DE system icon set; systems without an icon show their name
- Looping animated background video and theme music (**not included**, see below)
- Optional "grid" game-list view using the same tiles
- Matching icons in the START menu

The dots at the top are decoration only.

## Install
1. Put this folder in `/userdata/themes/` and name it exactly **BatWiiCeraU**
   (e.g. `git clone https://github.com/purplepeanut4/BatWiiCeraU /userdata/themes/BatWiiCeraU`;
   if you download the ZIP from GitHub, rename the folder).
2. On the device: START > User Interface Settings > Theme Set > **BatWiiCeraU**.

## Background video (not included)
The video is not part of this repo. Download it from Google Drive:
**https://drive.google.com/file/d/1KKF86j0RFLomnPrX_BBlACxxEb1SCjma/view**

The original is 2560x1440 at 60 fps, which is far too heavy for most Batocera devices. Convert it first
and save the result as `art/background.mp4`:

```
ffmpeg -i "Wii U Menu 16:9.mp4" -an -c:v libx264 -profile:v high -pix_fmt yuv420p \
  -vf "scale=1280:720,fps=30" -crf 25 -movflags +faststart art/background.mp4
```

It plays on the home screen only. Without the file you get a still background (`art/bg.jpg`).

## Theme music (not included)
Song link: https://downloads.khinsider.com/game-soundtracks/album/wii-u-system-audio-background-music/06.%2520System%2520Music%2520-%2520Wii%2520U%2520Home%2520Menu%2520%2528TV%2529.mp3

Save your song as `art/music/BatWiiCeraTheme.mp3`. It loops while you browse, and needs START > Sound Settings:
**Frontend Music = ON** and **Play System-Specific Music = ON**. To use a different file name, edit the
`<sound name="bgsound">` line in `theme.xml`.

## Credits and licenses
- **System icons:** [ES-DE-System-Icon-Set](https://github.com/Zoidburg13/ES-DE-System-Icon-Set) by Zoidburg13 (CC0)
- **Fallback console art, START-menu icons and the Cabin font:** [es-theme-carbon](https://github.com/fabricecaruso/es-theme-carbon)
  (Carbon v2.4 by Rookervik, based on "simple" by Nils Bonenberger; Batocera version by Fabrice Caruso), CC BY-NC-SA 4.0
- Because of Carbon, this theme is **CC BY-NC-SA 4.0**: attribution, non-commercial, share-alike. See `LICENSE.md`.
- Console logos and trademarks belong to their owners. This is a fan project, not affiliated with Nintendo.
