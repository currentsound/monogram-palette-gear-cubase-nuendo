# Monogram, Palette Gear + Cubase & Nuendo #

This is a collection of Monogram and Palette Gear Legacy assignments for Steinberg Cubase and Nuendo, version 5 or later, with Spitfire, VSL and typical film composing midi CCs. 

- To make it work with other daws, just edit the config.json and follow the structure/pattern to add support for your DAW, or disable automatic app switching in Monogram Creator so that you can use it in any DAW.
- You can also add support for other Kontakt libraries and 3rd party VSTis by adding the MIDI CCs + names you need to the presets.json file
- I also added a few unassigned MIDI CCs which you can use via the MIDI learn function in most instruments and it's fine to use a Spitfire or VSL MIDI CC for other instruments via the MIDI learn function
- This should in theory be future proof up until Cubase/Nuendo version 25

## Advantage of using a custom integration vs standard MIDI CCs

- Reading the manual for each library each time you want to add or change a MIDI CC assignment is time consuming
- Adding a new MIDI CC results in what it does being displayed on the fader or knob without you having to type it
- Using the Next and Previous buttons results in only scrolling Library and Synth profiles, not profiles for every app on your entire computer that you want to control with Monogram/Pallete Gear
- This repo contains important info to get your otherwise bricked Palette Gear and Monogram hardware working on Windows 11 and Mac OS. Which is good for the enviroment and your own happiness.

---

### Prerequisites ###

- For Monogram hardware[Monogram Creator](https://monogramcc.com/download/) (for monogram devices)
- For Palette Gear hardware, community supplied Google Drive backup of Monogram Legacy 4.1(https://vi-control.net/community/threads/beware-of-monogram-control-surface-company.153413/page-11)
- Cubase or Nuendo (version 4 or later)

---

## Setup Instructions ##

### Add Monogram as Generic Remote to Cubase ###

1. [Download and unzip latest release](https://github.com/currentsound/monogram-palette-gear-cubase-nuendo/releases); copy the unzipped folder to a safe location like your Documents folder.
2. Locate <code>Monogram + Cubase Generic Remote > MCC-GenericRemote.xml</code> inside downloaded package.
3. In the Cubase menu bar, go to Studio > Studio Setup. Select or add a Generic Remote and select 'Import'.
4. Import the <code>MCC-GenericRemote.xml</code> file as located in step 2 above.

### Add integration bundle to Monogram Creator ###

1. In Monogram Creator, go to File > Preferences > Integrations.
2. Hit the + button (lower right); this should open a file browser.
3. Browse for your <code>mono-cubase</code> folder, then double-click it to look inside for the <code>cubase</code> folder.
4. Choose the <code>cubase</code> folder, then hit "Open" (bottom right).


### Windows 11 driver fix ###

- You must do this if you're on Windows 11 or your hardware won't work anymore.

1. Open Device Manager (in Control Panel)
2. Expand the "Software Devices" dropdown menu
3. Look for "Palette Multi-function Device" in "Software Devices"
4. Disable the last one or two, leaving only one "Palette Multi-function Device" in "Software Devices"
5. Now MIDI output will work without crashing Cubase or your DAW.

- What I think this probably does is disables MIDI input, which is not used anyway as far as I know but now MIDI output will work without crashing the DAW. Because Windows 11 has an updated MIDI 2.0 driver built into the OS which did not exist at the time that this hardware and driver was built and there is most likely a conflict with this and MIDI input but luckily MIDI output works fine, provided that you do the above fix.

---

## Disclaimers ##

This is purely a homebrewed set of Monogram assignments for Cubase, forked and modified from  https://github.com/andyjhayes/mono-cubase. 

This is not a custom driver for Palette Gear/Monogram hardware. It still requires the Monogram Creator app and driver. Unless some clever person makes a custom open source driver and app, the hardware might stop working one day. This is more likely on Mac OS than Windows because it requires Rosetta on Mac which is rumored to not be available after Mac OS operating system number 28. Windows is likely less risky but still uncertain due to MIDI 2.0 evolving. Although I suspect it will likely keep working for many years on Windows x64 based systems.

A few things to keep in mind:

- It isn't developed or endorsed by either company. 
- It's provided with no warranty and it may not work on your system.
- Future Cubase or Monogram updates might break it.
- It's licensed under <a href="https://opensource.org/licenses/MIT">MIT</a>. Pull requests and issues are welcome :)

### Known Limitations ###

- Some assignments are unavailable or impossible with Orbiter inner disc (inherent incompatibility).
- Customize View in Creator > Module Settings window does not display Cubase Mode assignments. Please use Presets View > Cubase Mode or Customize View > MIDI Mode and Keyboard Mode in order to select your chosen assignments.

## Known Issues ##
- Cubase profiles seem to default back to regular MIDI command names and loose custom labels when using different hardware other than my personal hardware. This means you will likely need to create your own profiles for your own hardware. You can do this by clicking on a fader or button, going to MIDI CC then selecting the function on the library or synth which you wish to control. Then the labels for what that MIDI CC assignment will be shown on the fader without you having to guess what each fader does. Once you've done this, Monogram software will remember it as long as you don't delete the tab or try to re-load a saved profile. I recommend you don't delete any tabs and rely on buttons to switch profiles.
- Automatic switching to Cubase or Nuendo doesn't seem to be working for me. Not sure why. I'd suggest disabling the automatic switching of profiles by app in the settings. This will also allow you to use MIDI faders for the same VSTis in any DAW. If you create your own profiles by starting with "Cubase" then the "Next" and "Previous" buttons should only cycle through Cubase VSTs and Library profiles, without swapping to profiles for other apps. To access controls for other apps, you'll then have to open the monogram software and manually select it.
- Limitation of the main Monogram software, you must make it load when windows loads, or the hardware won't work. In Monogram Creator go to File=>Preferences=>Load When Windows Starts. You can also tick the "Close to system tray" checkbox on that screen and it will stay running when you close it. Stupidly it will not load minimized, you have to close it each time windows boots up for it to minimize.
- On Windows 11, using a fader for automation, you occasionally get a reading of 0, meaning it will write 0 briefly at a random time while moving the fader and you have to edit the MIDI CC out after recording to remove this. I don't know why it does this. It only happens sometimes while moving a fader and is very brief, like it will draw only one dot at the bottom while riding the fader. Testing: It's the same on multiple different Win 11 machines using different Pallete Gear hardware. If anyone finds a solution to this, let me know. Not sure if it's hardware or software/driver related but seems to occur on 6 different faders and two different Pallete Gear main brain/screens and on two different Win 111 systems, same outcome.


### Credits ###

- This is an up to date fork of the original repo https://github.com/andyjhayes/mono-cubase to add support for newer versions of Cubase/Nuendo plus Vienna Symphonic Library, Modern Scoring Strings and other VSTis.
