# rM2Mods

This is a collection of assets and scripts used to personalize a reMarkable2 e-ink tablet.

## Image Replacement

Different PNG files are used for various parts of the OS, all of which can be found in the device's `/usr/share/remarkable` directory.
The most common ones to modify are the `sleeping.png` and `suspended.png` images.

[More info for `sleeping.png`](https://github.com/DanielRunningen/rM2Mods/blob/main/assests/sleep/README.md)  
[More info for `suspended.png`](https://github.com/DanielRunningen/rM2Mods/blob/main/assests/suspension/README.md)

## Changing Default Settings

Some settings can be modified through minor changes in config files.

### Auto Sleep Timeout

The timeout for the "Auto sleep" setting is controlled by the `/home/root/.config/remarkable/xochitl.conf` file.
The `IdleSuspendDelay` variable is set to 1200000 milliseconds (20 minutes) by default.
Changing this value does not change the text describing the setting on the "Battery settings" page.

In order for the change to take effect, either restart the device or run the command:

```bash
systemctl restart xochitl
```

[[source]](https://www.reddit.com/r/RemarkableTablet/comments/8zarnq/standby_time/e2k0lcn?utm_source=share&utm_medium=web2x&context=3)

## Adding or Changing Templates

It's possible to add new or modify existing document templates. Doing so is only marginally more difficult than changing the `sleeping.png` or `suspended.png` from a technical standpoint. These files are stored in the `/usr/share/remarkable/templates` directory and are organized by the `templates.json` file found alongside the PNG and SVG files.

[More on templates](https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/README.md)
