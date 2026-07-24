# Monogram, Palette Gear + Cubase & Nuendo #

This is a collection of Monogram and Palette Gear Legacy assignments for Steinberg Cubase and Nuendo, version 5 or later, with Spitfire, VSL and typical film composing midi CCs. 

- To make it work with other daws, just edit the config.json and follow the structure/pattern to add support for your DAW.
- You can also add support for other Kontakt libraries and 3rd party VSTis by adding the MIDI CCs + names you need to the presets.json file
- I also added a few unassigned MIDI CCs which you can use via the MIDI learn function in most instruments

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

---

## Disclaimers ##

This is purely a homebrewed set of Monogram assignments for Cubase. A few things to keep in mind:

- It isn't developed or endorsed by either company. 
- It's provided with no warranty and it may not work on your system.
- Future Cubase or Monogram updates might break it.
- It's licensed under <a href="https://opensource.org/licenses/MIT">MIT</a>. Pull requests and issues are welcome :)

### Known Limitations ###

- Some assignments are unavailable or impossible with Orbiter inner disc (inherent incompatibility).
- Customize View in Creator > Module Settings window does not display Cubase Mode assignments. Please use Presets View > Cubase Mode or Customize View > MIDI Mode and Keyboard Mode in order to select your chosen assignments.

### Credits ###

- This is an up to date fork of the original repo https://github.com/andyjhayes/mono-cubase to add support for newer versions of Cubase/Nuendo plus Vienna Symphonic Library.
