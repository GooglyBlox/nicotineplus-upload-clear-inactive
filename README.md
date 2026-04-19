# Upload Clear Inactive

This Nicotine+ plugin adds one extra entry to the uploads `Clear All` menu:

`Cancelled / Failed / User Logged Off`

It clears uploads whose status is cancelled, failed, or user logged off, without clearing finished uploads.

<img width="458" height="545" alt="image" src="https://github.com/user-attachments/assets/3331a9c1-4f55-4ee3-95c5-51ebf676ab27" />

## What It Changes

Nicotine+'s default uploads clear menu already has individual entries for `Cancelled`, `Failed`, and `User Logged Off`. This plugin adds a grouped action for those three statuses in the grouped section at the top of the submenu.

## Tested Versions

This has been tested on Nicotine+ `3.3.10`, GTK `4.16.12`, and Python `3.12.9`.

Other Nicotine+, GTK, or Python versions may work, but this plugin relies on Nicotine+'s uploads menu internals and can break if that UI structure changes.

## Caveats

This is a UI monkey-patch. Nicotine+ does not currently expose a plugin API for changing this GTK menu, so the plugin waits for the uploads view, grabs `window.uploads.popup_menu_clear`, and rebuilds that submenu with the additional action.

If the uploads clear menu behaves strangely after enabling or disabling the plugin, disable it and restart Nicotine+.

## Installing

The intended install method is the zip from [GitHub Releases](https://github.com/GooglyBlox/nicotineplus-upload-clear-inactive/releases). Then, extract it into your plugins folder.

Once it's installed, enable `Upload Clear Inactive`, open the uploads tab, and give it a moment. The plugin waits for the window to exist, patches the uploads clear menu, and then adds the grouped inactive-clear option.

