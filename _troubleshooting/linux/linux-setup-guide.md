---
title: Setting up Final Fantasy XI on Linux Guide
layout: post
parent: Linux
---
How to set up Final Fantasy XI on Linux
========================================
<sub>Alternatively: Yet Another FFXI Linux Guide</sub>

###### Author: Arieh @ Bahamut

Setting up Final Fantasy XI on Linux can be frustrating for someone who is technical and far more so for a non-technical person, so here is a guide to help with that. If you find any of this daunting, I would recommend asking for help through the process. This game has a lot of issues on modern Windows PC's already, so it is completely ok to ask for help / check other guides if you have issues following this one, everyone's PC is different and what may have worked for me / others may not work for you on your PC for a completely unrelated reason.

Will also recommend the [Windower](https://discord.gg/aUrHCvk) / [Ashita](https://discord.gg/Ashita) Discord servers for being helpful places to ask when you run into technical issues on Linux. Please try to include all of the relevant information that you can when you ask for help (what you tried to do, what happened including error messages/screenshots/logs). Additionally in the Windower discord **you are prohibited from deleting your own messages**, this is just a server rule that they have and will remind you of.

And from this point onwards, I will be shortening Final Fantasy XI to FFXI in all cases.

## How do I install FFXI onto Linux?

### TL;DR (short guide)

Personally I recommend avoiding using Steam to install FFXI and instead installing via [Lutris](https://lutris.net/). Lutris has a bunch of scripts available for [installing Final Fantasy XI](https://lutris.net/games/final-fantasy-xi-online/) which you can use. If you are unsure of what version to install, I recommend using the `Full (US)` or `Full (EU)` option to install FFXI. When picking a Wine runner, Wine versions 9.15-9.21 and 10+ are good, and also any proton version 10.3 or newer. Some users have reported more success with the CachyOS builds of Proton but this is device/user dependent. Basically what works for you might not work for someone else. Additionally, some users reported memory leaks when using dgvoodoo2, so it can be worthwhile to set up atom0s' proxy (found in the Ashita discord). Ridge wrote a good guide for this (linked 2 sentences below) in their Ashita setup guide as well.

For Windower you can then install the `Windower 4 Live version` after this. There are also some extra steps and troubleshooting tips mentioned on the [Windower guide](https://docs.windower.net/linux/) as well if you run into any issues.

This guide will not cover installing Ashita after installing FFXI currently, but [Ridge's guide](https://bin.68degrees.no/?678efeeb84b354e8#5ehU14BvFHo5MBwSMJ4RBwRPwhW9QaF83BJiXR7E3CzL) for setting up FFXI on Linux with Ashita is a very good resource to follow.

### Long guide

For these guides, I did these steps on a Dell XPS 15 9560 laptop running Bazzite with the following specs, however I have also set up FFXI on SteamOS on my Steam Deck OLED using similar steps.

```
CPU: Intel Core i7-7700HQ 
Integrated GPU: Intel HD Graphics 630
Discrete GPU: NVIDIA GeForce GTX 1050 Mobile
Memory: 16GB
Locale: en_GB.UTF-8
```

#### Installing FFXI via Lutris

For *all* commands which require you to download or install packages, please check what you are installing/downloading before you install any software. 

This guide assumes you have not installed Lutris and that you use your PC in English. If you have installed Lutris already, you can skip the first step. This guide is also a prerequisite for setting up a copy of FFXI that uses Windower/Ashita on your Linux PC if you are unsure of what to do in this case. If you want to play FFXI in Japanese on Linux, unfortunately this guide does not cover this for the time being.

1. Install Lutris using the package manager for your distros. If you prefer using the GUI to install the packages, open that and use that to install Lutris. Otherwise here are some commands for popular distros/base distros if you wish to install from the terminal.
    * For debian-based distros: `sudo apt get update && sudo apt install lutris`
    * For arch-based distros: 
        * Using pacman: `sudo pacman -Sy lutris`
        * Using paru: `paru -Sy lutris`
        * For CachyOS users: Install both of the packages mentioned on [this page](https://wiki.cachyos.org/configuration/gaming/) on their wiki if you have not already. Despite being packaged separately, the `cachyos-gaming-meta` package is a requirement.
    * For Fedora-based distros: `sudo dnf install lutris`
    * For Bazzite, Lutris should be preinstalled by default, but if it is not installed you can download it from the Bazaar application.
2. Open up Lutris and click on the `+` button in the top left hand corner.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20250909_121312.png)
3. A new window will open, click on the first option `Search the Lutris website for installers`.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20250909_121344.png)
4. Enter the search term `Final Fantasy XI Online` and click on the first option.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20250909_121520.png)
5. Once the next page loads with the options of what version to pick, pick `Full (US)` and click install.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20250909_121834.png)
6. It will now prompt you to pick an install location (use the default if you are unsure) and whether you want to create shortcuts elsewhere on your system for this. Click `Continue` to proceed to the next screen.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20250909_122128.png)
7. Lutris will now ask you whether you wish to provide files locally or whether it should download the files while doing the install process. Unless you're on a metered internet conneciton, I recommend downloading the files fresh so that it can install a fresh copy of FFXI. Currently this download is around 7.5GB.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20250909_122131.png)
8. Click `Install` to begin the installation process. This will take some time (like possibly 15 - 20 minutes), so just keep an eye on it for any errors that may occur during the installation process.
    * If errors do occur, check below in the Troubleshooting selection to see if your error was covered otherwise copy the error log to a text file and have it handy for if someone asks "what error happened?"
9. If no errors occurred and you see the following screen, then you now have a copy of FFXI installed onto your PC! 

#### Configuring FFXI in Lutris

#### Installing and configuring Windower in Lutris

This guide assumes that you have a copy of Final Fantasy XI Online already set up via Lutris.

1. Open up Lutris and right click on your existing install of Final Fantasy XI Online and click the option `Install another version`.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20260111_174559.png)
2. Look for the option called `Windower 4 Live` in the list and click `Install` on that option.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20260111_174924.png)
3. It will now prompt you to pick a source for installing Windower 4, similar to how you picked the install file location for when you were installing FFXI. Click `Install` to continue, this will download the latest version of `Windower 4` directly from the Windower website.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20260111_174924.png)
4. Lutris will now install `Windower 4` based on your already existing FFXI installation.
5. After that, you should see `Windower 4` in the main window on Lutris and can launch Windower from there.

## FAQ

### Should I use dgvoodoo2 from Lutris?
While it can work in some cases, you should not use versions higher than v2.8.2, they will not work at all. Ideally if the game works with just dxvk, then you should be ok. 

### Which wine/proton version should I use?
There are various versions you should not use without specific fixes due to a stuttering issue that exists in some versions of Wine. From experience / other members of the FFXI Community, these are the versions of Wine/Proton that people will generally recommend for playing FFXI with.

* Wine `9.15-9.21` or `10.x`
* `GE-Proton-10-15` or `GE-Proton-10-21` 

#### Important note for when you bind a controller
If you are trying to bind a controller to your copy of FFXI and use a version of Proton/Wine with version number 9 or newer, you may need to an older version of Proton/Wine in order to bind your controller at all. Newer versions of Proton will hijack your gamepad inputs for dialog boxes and this can make binding them legitimately impossible. 

Using an older Proton version will work, I personally used the following version below, but I think that any older wine version will work for setting this up.
![Lutris window](/assets/images/troubleshooting/linux-guide/Screenshot_20260111_180210.png)
*Wine version selected in the window currently is `wine-ge-8-26-x86_64`*

### Should I change my Linux distribution to make FFXI run better?
No. Usually the Linux distribution does not matter so much for making FFXI run better and this is not something that is recommended to do in any case. If you wish change distribution, just make a copy of the `Final Fantasy XI Online` folder so that you do not have to redownload all the patches every time you reinstall the game.  

## Troubleshooting

### What is the rundll32.exe error I see when launching FFXI sometimes?
Usually if you change the wine version you use, or are launching a fresh install of FFXI for the first time, there will be a dialog box which opens (as shown in the image below) that states that the application `rundll32.exe` could not be started. You can click `No` on this dialog box and then the game should launch as normal.

![rundll32.exe window](/assets/images/troubleshooting/linux-guide/Screenshot_20260111_175921.png)

### Why does the FFXI install in Lutris fail?

#### Sanity checks
* Make sure some form of `wine` is installed separately to Lutris. 
* Please set the default Wine version to the `System` Wine and not the wine version lutris installs automatically.
* Disable any VPN connections during the download step, or download the files separately. This is because GitHub will block connections over VPNs automatically. 

#### The downloaded files already exist.
You can either clear the files from the Lutris cache, or you can link to them directly when trying to install FFXI.

#### Error log shows "Accessing game config while runner wasn't given one."
* The default Lutris wine runner occasionally has issues with setting up this game depending on distribution because Lutris will install it's own version of Wine which may not have all the same permissions as Wine installed directly onto your system.
* You can change the default wine runner with the following steps:
    1. Open Lutris
    2. Open Preferences within Lutris
    3. Click on the Runners tab
    4. Scroll down to Wine and click on the left button on the right hand side
    5. In the tab `Runner options`, set the Wine version to `System (10.x)`

## I've installed FFXI but my game won't launch, what should I check?

TODO: add this

## Glossary

Will add basic explanations of terms used in the guide for those who are unaware of what the terminology means.

### Distro / Distribution
    * Distrubtion (often abbreviated as distro) is an operating system that includes the Linux kernel for its kernel functionality and is commonly used to refer to different versions of Linux that people may use. Popular ones include Debian, Ubuntu, Pop_OS!, Arch Linux and Fedora. Popular gaming-focused distros are Bazzite (based on Fedora), CachyOS (based on Arch Linux), SteamOS (based on Arch Linux) and Nobara (based on Fedora).

### Wine

WINE is an acronym for WINE Is Not (an) Emulator. It is a compatibility layer which lets Windows programs run on Linux.

### Proton

Valve's gaming-focused fork of Wine which is the backbone of Linux gaming as we know it today. There are a few different forks of Proton as well, but these are less used by the wider community except in specific cases. 

### Lutris

Lutris is a game manager which lets you manage installing & configuring games on your Linux system.
