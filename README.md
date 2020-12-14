# rM2Mods

This is a collection of assets and scripts used to personalize a reMarkable2 e-ink tablet.

## Image Replacement

Different PNG files are used for various parts of the OS, all of which can be found in the device's `/usr/share/remarkable` directory.
The most common ones to modify are the `sleeping.png` and `suspended.png` images.

[More info for `sleeping.png`](https://github.com/DanielRunningen/rM2Mods/blob/main/assests/sleep/info.md)  
[More info for `suspended.png`](https://github.com/DanielRunningen/rM2Mods/blob/main/assests/suspended/info.md)

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
