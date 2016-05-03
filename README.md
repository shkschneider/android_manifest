# ShkMod

> A modest custom ROM based off [AOSP](https://android.googlesource.com/) with minimal modifications.

I started cooking ROMs with _Android 2.2 FroYo_ and _Android 2.3 Gingerbread_ mainly.
Over the years, I felt more and more satisfied with the community's work, yet the stock "pure" Nexus experience was more and more pleasant by itself.

Android getting more and more mature, starting with _Android 6.0 Marshmallow_ (and its _Material Design_), I felt like having a stock "pure" Nexus experience, while having root, could be enough for me.

I was wrong: it lacked tiny things here and there. So I made this modest ROM with the few things I missed from the custom ROMs. And that is enough for me.

My work is licensed under the [Apache 2](http://www.apache.org/licenses/LICENSE-2.0.txt) license.

## Versions

* **ShkMod: 16.05.00**
  * Format: _YEAR.MONTH.DAY_ (follows the latest integrated [Android Security Bulletins](http://source.android.com/security/bulletin/index.html))
  * _DAY_=00 means a work-in-progress.
  * Final release has the day of the _Android Security Bulletin_ as last digits (> 00).
  * Subsequent updates might appear, incrementing the last digits even more.
* **Android: 6.0.1** [android-6.0.1_r30](https://source.android.com/source/build-numbers.html#source-code-tags-and-builds)

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
- Quick switch to last app (by long-pressing the recents tasks button)
- (Optional) Pin scramble
- System UI Tuner enabled by default (icon invisible from status bar)
- Speed up animations by 25%
- Accepts Google's WebView as alternative
- Displays applications' names while optimizing during boot
- Open GApps permissions
- Disabled OTAs
- Does not flash recovery
- Refreshed stock icons
- (Configurable) Smart Quick Settings pull-down
- Keyboard supports gesture input (native library provided)

### Scripts

* _vendor/shk/androids.sh_: lists all AOSP branches (version sort)
* _vendor/shk/build.sh_: builds _ShkMod_
* _vendor/shk/envsetup.sh_: minimalist envsetup for emulator target
* _vendor/shk/update.sh_: updates _ShkMod_ repositories from AOSP (pull)

### See

* https://github.com/shkschneider/android_build
* https://github.com/shkschneider/android_frameworks_base
* https://github.com/shkschneider/android_packages_apps_Settings
* https://github.com/shkschneider/android_packages_inputmethods_LatinIME
* https://github.com/shkschneider/android_vendor_shk

## Devices

List of available (configured) targets (devices):
<pre>$ ./vendor/shk/build.sh
...</pre>

_This work could very easily be ported to any other Nexus device, maybe even other devices &mdash; this is AOSP, a solid build for Nexus devices and a solid base for other devices (modulo the proprietary blobs)._

## Clone

Regular [AOSP download](https://source.android.com/source/downloading.html):
<pre>$ repo init --config-name -u https://android.googlesource.com/platform/manifest -b android-6.0.1_r30</pre>
Clone this repository (alters AOSP):
<pre>$ git clone https://github.com/shkschneider/android_manifest.git -b shk-marshmallow .repo/local_manifests</pre>
Sync:
<pre>$ repo sync</pre>

## Build

### For emulator

_The build process has only been tested on Linux x86_64._

<pre>$ ./vendor/shk/build.sh shkmod_emulator-eng</pre>

This makes the images to be used by the emulator (64-bits only).
<br />Run the last given command to start it and try the ROM on the emulator.

### For device

<pre>$ ./vendor/shk/build.sh shkmod_hammerhead-user
...
rom-shkmod-{device}-{ro.mod.version}-{revision}-{buildId}.zip
stock-shkmod-{device}-{ro.mod.version}-{revision}-{buildId}.zip</pre>

The _rom-*.zip_ file is what you would want to flash on your device using a custom recovery.
<br />The _stock-*.zip_ file contains all final images that you might want to use with _fastboot_.

## AOSP Apps

- Downloads
- Email
- Gallery
- Phone
- Settings

Indeed, apps were removed.

_shkmod_emulator-eng_ target adds back a lot of AOSP apps for testing purposes.

## Google Apps

This ROM comes _without_ Google Apps. [Open GApps](http://opengapps.org) are recommended.

## Credits

For this ROM:
- [AOSP](https://android.googlesource.com/) (and [Open Handset Alliance members](http://www.openhandsetalliance.com/oha_members.html))
- [Chroma-Aosp](https://github.com/Chroma-Aosp) (mainly [zephiK](https://github.com/zephiK))
- [CyanogenMod](https://github.com/CyanogenMod)
- [Google](https://developers.google.com/android/nexus/drivers)
- [OpenGApps](http://opengapps.org) ([Google Swipe library](https://github.com/opengapps/opengapps/wiki/Stock-Package))
- [TeamExodus](https://github.com/TeamExodus) ([OpenGApps support](https://github.com/opengapps/opengapps/wiki/Notes-for-Android-6.0))

For everything else:
- [XDA-Developers](http://forum.xda-developers.com) ([2398805](http://forum.xda-developers.com/member.php?u=2398805))
