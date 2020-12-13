# rM2Mods

This is a collection of assets and scripts used to personalize a reMarkable2 e-ink tablet.

## Image Replacement

Different PNG files are used for various parts of the OS, all of which can be found in the device's `/usr/share/remarkable` directory.
The most common ones to modify are the `sleeping.png` and `suspended.png` images.

### `sleeping.png`

By default, the `sleeping.png` image is invoked after the device has been left alone for 20 minutes.
This feature can be turned off in the device settings under the "Battery" section's "Auto sleep" toggle.

The original image is just a black, 120 pixel tall banner across the top of the device that reads "Press button to continue" in a white, sans-serif font.
The rest of the page is taken up by the contents of the screen that were last visible prior to enabling sleep mode.
This is helpful if you want a particular page mostly visible as a reference, but would like to limit battery usage.

Replacement images for this feature are found in the `assets/sleep` directory of this repo.

Example:

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/sleep/opaqueZsBorder.png" width="15%" />

### `suspended.png`

The default `suspended.png` image is a white canvas with black text in the center that reads "reMarkable is sleeping", which leads to some confusion in regards to the file's name.
`suspended.png` is the correct file name.
This image is invoked when a user physically presses the device button or the device sits in the sleeping state for an extended period of time.

Replacement images for this feature are found in the `assets/suspension` directory of this repo.
Example:

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/suspension/sebastian.png" width="15%" />

## Changing Default Settings

Some settings can be modified through minor changes in config files.

### Auto Sleep Timeout

The timeout for the "Auto sleep" setting is controlled by the `/home/root/.config/remarkable/xochitl.conf` file.
The `IdleSuspendDelay` variable is set to 1200000 milliseconds (20 minutes) by default.
Changing this value does not change the text describing the setting on the "Battery settings" page.

In order for the change to take effect, either restart the device or run the comand:

```bash
systemctl restart xochitl
```

[[source]](https://www.reddit.com/r/RemarkableTablet/comments/8zarnq/standby_time/e2k0lcn?utm_source=share&utm_medium=web2x&context=3)
