## Table of contents
1. [Introduction](#introduction)
2. [What is MacroQuest2?](#whatis)
3. [Disclaimer](#disclaimer)
4. [Setup](#setup)
5. [Getting Started](#getting-started)

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

1. If you want to multi-box, first run `EQBCS2.exe` to start the chat server between your characters. This will start a console that should contain something like this:

   ```shell
   EQ Box Chat Server 10.12.18
   Waiting for connections on port: 2112...
   ```
