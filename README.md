# ShkMod

> A modest custom ROM based off [AOSP](https://android.googlesource.com/) with minimal modifications.

I started cooking ROMs with _Android 2.2 FroYo_ and _Android 2.3 Gingerbread_ mainly.
Over the years, I felt more and more satisfied with the community's work, yet the stock "pure" Nexus experience was more and more pleasant by itself.

Android getting more and more mature, starting with _Android 6.0 Marshmallow_ (and its _Material Design_), I felt like having a stock "pure" Nexus experience, while having root, could be enough for me.

I was wrong: it lacked tiny things here and there. So I made this modest ROM with the few things I missed from the custom ROMs. And that is enough for me.

My work is licensed under the [Apache 2](http://www.apache.org/licenses/LICENSE-2.0.txt) license.

## Devices

List of available (configured) targets (devices):
<pre>$ ./vendor/shk/build.sh</pre>

- hammerhead (Nexus 5)
- emulator (x86_64)

_Although this work could very easily be ported to any other Nexus device._

## Features

- (Optional) Music rocker (skip tracks while screen is off)
- (Optional) Quick Settings one-finger pull-down (right side of the status bar)
- Advanced reboot
- Long press back kills foreground app
- No ADB notification
- Security enhancements
  - Password invisible by default
  - Screen locks immediately when off by default
- No IME notification
- (Optional) Hide brightness slider
- Quick switch to last app (alt-tab alternative by long-pressing the recents tasks button)
- (Optional) Pin scramble
- System UI Tuner enabled by default (icon invisible from status bar)
- Speed up animations by 25%
- Accepts Google's WebView as alternative
- Displays applications' names while optimizing during boot
- Open GApps permissions
- Disabled OTAs
- Do not flash recovery
- Refreshed stock Dialer
- _vendor/shk/build.sh_ bash script
- _vendor/shk/androids.sh_ bash script

See:
* https://github.com/shkschneider/android_build
* https://github.com/shkschneider/android_frameworks_base
* https://github.com/shkschneider/android_packages_apps_Dialer
* https://github.com/shkschneider/android_packages_apps_Settings
* https://github.com/shkschneider/android_system_core
* https://github.com/shkschneider/android_vendor_shk

## Credits

For this ROM:
- [AOSP](https://android.googlesource.com/)
- [Chroma-Aosp](https://github.com/Chroma-Aosp)
- [TeamExodus](https://github.com/TeamExodus)
- [Google](https://developers.google.com/android/nexus/drivers)

For everything else:
- [CyanogenMod](https://github.com/CyanogenMod)
- [XDA-Developers](http://forum.xda-developers.com)

## Build for emulator

<pre>$ ./vendor/shk/build.sh shkmod_emulator-eng
[ ShkMod XX.XX.XX ]
[ Android X.X.X XXXXXX ]
  API: XX
  BuildId: XXXXXX
  Revision: android-X.X.X_rXX
  SecurityPatch: XXXX-XX-XX
[ Target: shkmod_emulator-eng ]
  Device: emulator
  Variant: eng
[ Cleaning... ]
  make installclean
[ Building... ]
  make droid
...
[ source vendor/shk/envsetup.sh && ./prebuilts/android-emulator/linux-x86_64/emulator -skin WVGA800 -memory 2014 -gpu on -sysdir out/target/product/generic_x86_64 -sdcard out/target/product/generic_x86_64/sdcard.img ]
Done in XXX seconds, using XXX of (X) CPU resources.
</pre>

This makes the images to be used by the emulator. Run the last given command to start it and try the ROM on the emulator.

## Build for device

<pre>$ ./vendor/shk/build.sh shkmod_hammerhead-user
[ ShkMod XX.XX.XX ]
[ Android X.X.X XXXXXX ]
  API: XX
  BuildId: XXXXXX
  Revision: android-X.X.X_rXX
  SecurityPatch: XXXX-XX-XX
[ Target: shkmod_hammerhead-user ]
  Device: shkmod_hammerhead
  Variant: user
[ Cleaning... ]
  make installclean
[ Building... ]
  make dist
...
[ Assembling... ]
  sign_target_files_apks
  - signed-shkmod-XX.XX.XX-android-X.X.X-XXXXXX.zip
  ota_from_target_files
  - ota-shkmod-XX.XX.XX-android-X.X.X-XXXXXX.zip
[ Finalizing... ]
  updater-script
  build.prop
  recovery
[ rom-shkmod-XX.XX.XX-android-X.X.X-XXXXXX.zip   xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx ]
[ stock-shkmod-XX.XX.XX-android-X.X.X-XXXXXX.zip xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx ]
  http://opengapps.org
Done in XXX seconds, using XXX of (X) CPU resources.</pre>

The _rom-*.zip_ file is what you would want to flash on your device using a custom recovery.
The _stock-*.zip_ file contains all final images that you might want to use with _fastboot_.

## Google Apps

This ROM comes _without_ Google Apps. [Open GApps](http://opengapps.org) are recommended.
