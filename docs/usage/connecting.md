---
layout: default

title: Connecting
parent: Usage
nav_order: 1
---


# Connecting to an audio system
HouseCurve measures your audio system by listening to it play a test signal.  There are several ways to send the test signal to the audio system as shown in the diagram below.

![connecting housecurve](/assets/img/connecting_housecurve.png "Connecting HouseCurve to audio system")


## Airplay or Bluetooth

HouseCurve can connect to the audio system wirelessly using AirPlay or Bluetooth. Tap <img src="/assets/img/airplay.png" alt="AirPlay" class="app-icon"> at the top right of the screen to see a list of wireless outputs.

Connections established using the iOS Control Center or Apple Music are not recognized by HouseCurve (Apps that play and record are not permitted to use the buffered AirPlay v2 used by music apps).

Some implementations of AirPlay and Bluetooth struggle with short segments of audio and will not work with HouseCurve.  This can be compounded by long playback delay/buffering, for example, running a convolution engine (FIR filters).

**Note - AirPlay v1 was broken in iOS-18.4.x, this prevented HouseCurve from connecting to AirPlay devices.  This issue was resolved in iOS 18.5**

If you encounter problems with wireless connections, try a wired connection or external stimulus.


## Wired

HouseCurve automatically detects and uses USB audio and analog (ex: [Lightning to 3.5mm adapter](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jack-adapter)) connections.  Wired connections override wireless ones.


## External stimulus

With this method, the audio system is responsible for playing the test signal and HouseCurve will listen for it when measure is tapped.  Use when direct connection is not possible, or if wireless methods are not working.

The [test signal](../manual/file_formats.md#test-signal) can be downloaded by going to [Measure Setup](../manual/measure_setup.md) of the Sweep or Real Time tools and enabling external stimulus.  The [channel settings](../manual/measure_setup.md#channels) for the measurement tool are used to generate the file.  Note - the Real Time test signal is about one minute long, use looped playback if you need more.

The test signal file can be saved to any network drive visible to the iPhone/iPad (iCloud, Samba, etc).  Alternatively, you can save locally and share with text message, email, AirDrop, etc.

HouseCurve must stay in the foreground when taking measurements (iOS restriction).  If you need to use your iPhone/iPad to trigger audio system playback, use looped playback.  You can then switch back to HouseCurve and capture measurements as needed.

It is not possible to measure audio streamed from an app running on the same iOS device, ex: to adjust the Spotify equalizer.  In this situation, use a separate iOS device running HouseCurve to measure.

When external stimulus is enabled, wired connections are ignored and the AirPlay button will be disabled.


## HouseCurve on macOS

HouseCurve _can_ be used on a macOS computer with Apple silicon (ex M1 chipset), however it is not currently supported.  Audio input/output must be controlled through the system sound settings, not the app itself.  Mac microphones have not been tested for use with HouseCurve. An external microphone is recommended.



