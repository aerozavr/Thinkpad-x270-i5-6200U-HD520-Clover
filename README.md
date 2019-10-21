# Lenovo Thinkpad x270s-Clover
Clover Bootloader, Kexts, config and ACPI patches for ThinkPad x270.
Based on nicogig's repo: https://github.com/nicogig/T460s-Clover which is based in https://github.com/tluck/Lenovo-T460-Clover repo from tluck.

## What's different from nicogig's Clover config
- Audio device id different.Change the Inject value to 29.**Solve the sound card sound is very small (almost inaudible) problem** 
 _(different batches of computers, this value may be different, try in the following range: 3, 11, 13, 28, 29, 30, 47, 66, 72, 99, and restart the computer to try)_
- **Delete the wrong line in config.list**: _<string>kext-dev-mode=1</string>_
- **Solve the problem that external HDMI monitor does not respond**, add board-id key-value in config.list._(Where the value of board-id comes from:Visit to da to folder "/ System/Library/Extensions/AppleGraphicsControl kext/Contents/PlugIns/AppleGraphicsDevicePolicy kext/Contents/Info. The plist", to copy out the document (not directly edit permissions), using a text editor to open, see the multi-line format for "Mac - * * * * * * * *" key,The value below is Config2 or none. Select a key whose value is "none" as the value of the "board-id" above._

## What's working
Pretty much everything that's working with tluck's config, with the addition of multitouch, Force Touch (emulated) and the LTE Modem.

## What's not working
- SD Card reader
- Physical mouse buttons

## Testing
The config uploaded here was tested on a ThinkPad x270 with an i5-6200U CPU, Intel HD Graphics 520 GPU, 8GB RAM, 256GB NVMe Drive and a FHD Screen. 
**MacOS version** :
- [macOS Mojave 10.14.6 18G87](https://blog.daliansky.net/macOS-Mojave-10.14.6-18G87-Release-version-with-Clover-5033-original-image.html) A lower version might be fine, too.
- macOS Catalina 10.15 19A583 or later hasn't been tested yet, but it should work.

## Credit
Thanks to nicogig and tluck for laying the groundwork for a working hackintosh on the different t460x variants. I'd also like to thank RehabMan, Shmilee, vusun123, TimeWalker, Mieze, 黑果小兵 and every other hacker who makes Hackintoshing possible.
