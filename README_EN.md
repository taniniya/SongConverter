# SongConverter

A customized version of the TJA toolset for Taiko no Tatsujin simulators (SongSorter / DanGenerator / DanConvertor).

日本語: [README.md](README.md)

## About

This is a customized version based on SongConvertor by bluetaiko. Since the original repository was deleted, this repository publishes an improved-UI build based on a fork.

## Download

Download `SongConverter-v1.2.0.exe` from [Releases](https://github.com/taniniya/SongConverter/releases). It is a self-contained single file with the .NET runtime included, so it runs on Windows as-is (no installation required).

## Features

### SongSorter
Organizes TJA files copied from esegit into the same order as the official game.

### DanGenerator
Creates Dan (Dan-dojo) files compatible with TaikøNauts, etc., using the Dan name and conditions from the Taiko Wiki Dan page.

### DanConvertor
Converts TJA Dan files (from OpenTaiko, etc.) into Dan files compatible with TaikøNauts, etc.

## How to use

### SongSorter
1. In the **AddSongs** tab, select the parent folder where you want to download songs and click the "Add Songs" button. (If Git is not installed, please install it from https://git-scm.com/)
2. In the **SongSorter** tab, select the source **Songs** folder and the destination **Songs** folder.
3. Click the **Start Sorting** button.

### DanGenerator
1. Enter the URL of the Taiko Wiki Dan page. (e.g., https://wikiwiki.jp/taiko-fumen/%E6%AE%B5%E4%BD%8D%E9%81%93%E5%A0%B4)
2. Decide the output folder.
3. Select the **Songs** folder.
4. Click the **Generate Dan** button.

### DanConvertor
1. Select the TJA file(s) you want to convert.
2. Decide the output folder.
3. Select the **Songs** folder (Optional).
4. Click the **Convert** button.

*Note: Specifying difficulty automatically was technically difficult due to the TJA structure. Please manually specify the difficulty by changing the "difficulty" value in "danSongs". (0: Easy, 1: Normal, 2: Hard, 3: Oni, 4: Ura-Oni)*
By default, as long as you don't select a simulation folder, the Dan TJA will be split so that you don't have to specify the difficulty manually.

## Changes in this custom version

### v1.2.0
- **Modern UI redesign**: the top tab strip is gone, replaced by a left sidebar + header layout that looks like a recent Windows app
- Rounded buttons, Windows 11 rounded window corners, a brighter red accent palette, more spacing and the Yu Gothic UI font

### v1.1.0
- **Larger progress panel**: a big always-visible panel above the log shows the current step in bold, plus percent, processed/total counts and elapsed time. The final state stays visible after the operation finishes
- **SongSorter progress wired up**: the core already had a progress callback that the app never used; it now drives the progress bar. Song-list fetching also reports per-category progress
- **Dark theme**: dark gray UI with taiko-red action buttons, a red underline on the selected tab, and a terminal-style log (green text on black)
- **New icon**: a taiko drum with drumsticks and a music note
- **Updater target changed**: update checks now look at this repository (taniniya/SongConverter) instead of the deleted original

## Building

Requires the .NET 10 SDK.

```
dotnet publish SongConverter.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:EnableWindowsTargeting=true
```

## Credits / License

- Original: SongConvertor by bluetaiko
- License: MIT License (see [LICENSE](LICENSE))
