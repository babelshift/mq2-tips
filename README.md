## Table of contents
1. [Introduction](#introduction)
2. [What is MacroQuest2?](#whatis)
3. [Disclaimer](#disclaimer)
4. [Setup](#setup)
5. [Getting Started](#getting-started)
6. [Basic Use](#basic-use)

## Introduction <a name="introduction"></a>
The page is being created to act as a beginner's guide to MacroQuest2 (MQ2). As I learn more about its functions, I will be documenting my findings here in a no-nonsense and easily understandable layout for even the most tech illiterate among us.

## What is MacroQuest2? <a name="whatis"></a>
MacroQuest2 (MQ2) is a customizable application to perform automatic actions within EverQuest. It allows for automating tasks such as casting spells, character movement, looting corpses, responding to dialog boxes, and a lot more. The ecosystem is wide ranging and allows for customizing nearly any type of action in the game. In fact, you can further customize MQ2 by writing your own macros, scripts, and plugins.

## Disclaimer <a name="disclaimer"></a>

Using MQ2 violates user agreements in some scenarios. I wouldn't suggest using MQ2 on EverQuest Live servers or emulated servers that explicitly ban its use. If you do, you have only yourself to blame if or when you are banned.

## Setup <a name="setup"></a>
### Word of Warning

Before you rush out there to download MQ2, please be aware that there are various ways to obtain it, and the differences between those ways are important to understand. 

There are many different releases of MQ2 which must be compatible with the EverQuest client you plan to use. For example, there are different MQ2 distributions for the RoF2 client than the Titanium client. MQ2 won't work if you try to use an incompatible version.

In addition, the various EverQuest communities have "sanctioned" compiled releases of MQ2 which contain very specific sets of plugins by default. For example, the EQEmu "PEQ" server doesn't allow plugins that facilitate teleportation, speed hacks, or 100% automated bots. That community has compiled and released a bundle of MQ2 which excludes those plugins.

Keep this in mind as you search around for the community you want to join. If you're setting up your own server, then you can basically do whatever you want (provided you are following the client-specific caveat discussed above).

### Extracting MQ2

After downloading the release of your choice, extract the package to wherever is convenient for you. In the extracted folder, you should see a `Macros` folder, `EQBCServer.exe`, `MacroQuest2.exe`, and a bunch of `dll` files. If you don't see these, then you might have a weird build.

### Common Folders and Files

- `Macros` folder:
  - Used to house scripts used by MQ2 and any custom scripts that you want to use as part of your play session
- `EQBCS2.exe`
  - EverQuest Box Chat Server
  - Facilitates communication between all characters which are connected to the server
  - Only necessary to use if you want to multi-box and send commands from one box to another
- `MacroQuest2.exe`:
  - Main executable for MQ2
  - Required to be running when you launch EverQuest so that the process can be injected into the EverQuest runtime
- Various `dll` files: 
  - Libraries used by MQ2 internals and plugins developed by the community to accomplish specific tasks
  - For some limited examples:
    - `MQ2MoveUtils.dll` provides advanced movement automation
    - `MQ2Twist.dll` provides automated bard song twisting
    - `MQ2AutoGroup.dll` provides automated group invite and accept across multi-boxes

## Getting Started <a name="getting-started"></a>

Before you go crazy downloading all sorts of extra plugins and researching how to write macros, I would highly suggest just running the vanilla release of MQ2 with your EverQuest client to ensure things are going to work as you expect.

1. If you want to multi-box, launch `EQBCS2.exe` (sometimes also known as `EQBCServer.exe`, `EQBCS.exe`, and `MQ2EQBCS.exe`) to start the chat server between your characters. This will start a console that should contain something like this:

   ```shell
   EQ Box Chat Server 10.12.18
   Waiting for connections on port: 2112...
   ```

   Note that you might need to update the `MQ2EQBC.ini` config file to contain the correct IP address for the chat server to listen on. 

   `MQ2EQBC.ini`

   ```ini
   [Last Connect]
   Server=<ip_address>
   Port=2112
   ```

   If you want to multi-box across different computers, the `<ip_address>` should be something that computers on your local network can connect with (ie. your computer's network IP address as setup in your router). If you only want to multi-box on a single computer with multiple instances of EverQuest, then the `<ip_address>` should be `127.0.0.1` to indicate connections to your `localhost`.

2. Regardless of what you do with Step #1 above, you will need to launch `MacroQuest2.exe` to start the MQ2 process. There is no immediate visual indication that it is running, so make sure you check in your system tray (lower right corner on Windows) to see the MQ2 icon.

3. After confirming that MQ2 is running, launch EverQuest. When you get to the character select screen, you should see a new chat box popup which indicates that MQ2 has been injected to the EverQuest client and is running successfully. If you don't see this, make sure MQ2 is actually running (Windows notification tray icon) and make sure it's a version of MQ2 which is compatible with your EverQuest client.

4. Select your character, enter the world, and notice as there is a new window titled `MQ`. This is the command window which will output all information about MQ2, your plugins, and macro outputs.

## Basic Use <a name="basic-use"></a>

MQ2 has built in default commands and a lot of extended commands as part of the various plugins. Depending on the server you want to play on, not all commands and plugins will be supported or allowed. Below are some common commands to be used in the MQ2 chat box.

`/keypress <key_name> <options> `

- Simulates pressing the `<key_name>` key with various `<options>`
- `<key_name>` can refer to an actual key on the keyboard or to an alias as defined by the `/bind` MQ2 command or built in EQ binds
- `/keypress h` will simulate pressing the `h` key (by default will translate to the EQ bind for "hail")
- `/keypress forward hold` will simulate pressing the EQ bind for forward movement and will hold that key down
- `/keypress forward` will simulate tapping the EQ bind for forward movement

### EQBC Specific Commands

`/bc`

`/bca`

`/bcaa`

`/bct`
