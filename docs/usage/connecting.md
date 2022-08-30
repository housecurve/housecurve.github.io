---
layout: default

title: Connecting
parent: Usage
nav_order: 1
---


# Connecting to an audio system
HouseCurve sends a test signal to your audio system and measures the result using a microphone. This is shown in the diagram below.

![connecting housecurve](/assets/img/connecting_housecurve.png "Connecting HouseCurve to audio system")

HouseCurve can connect to the audio system wirelessly using AirPlay or Bluetooth. Tap <img src="/assets/img/airplay.png" alt="AirPlay" class="app-icon"> at the top right of the screen to see a list of wireless outputs.

Alternatively, the headphone connector can be used to create a wired connection to the audio system.  Use a [Lightning to 3.5mm adapter](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jack-adapter).

If direct connection is not possible, or isn't working, HouseCurve can use [externally played sweeps](../manual/measure_setup.md#external-sine-sweep).  In this mode, the audio system is responsible for playing the test signal and HouseCurve listens for it when measuring.  The test signal must be manually transferred to the audio system (ex: SD card, CD, streaming library).


## AirPlay connections

To use HouseCurve with AirPlay, you must tap <img src="/assets/img/airplay.png" alt="AirPlay" class="app-icon"> at the top right.  Connections established using the iOS Control Center or Apple Music are not recognized by HouseCurve (this is an iOS limitation related to long form audio and recording).  Note - this button is disabled when using externally played sweeps.

## AirPlay and buffering

Some implementations of AirPlay struggle with short segments of audio and will not work with HouseCurve (currently).  This can be compounded by systems that introduce a lot of delay in the playback, such as a systems running a convolution engine (FIR filters).

If you encounter problems with AirPlay, try using [externally played sweeps](../manual/measure_setup.md#external-sine-sweep) or a Bluetooth connection.  And, please [let me know](mailto:support@housecurve.com) as this helps me develop a more robust solution.

