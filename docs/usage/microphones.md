---
layout: default

title: Microphones
parent: Usage
nav_order: 2
---

# Microphones
HouseCurve was designed to work with built in iPhone / iPad microphones (aka "internal microphones").  By default, HouseCurve will use the bottom mic on an iPhone and the top mic on an iPad.  If an external microphone is connected, HouseCurve will use that instead.

The following settings change how HouseCurve chooses microphones:

* [Internal Mic Location](../manual/measure_setup.md#internal-mic-location)
* [External Mic Enable](../manual/measure_setup.md#external-mic-enable)


## Internal Micrphones

The iPhone/iPad microphones have a surprisingly flat response and are quite acceptable for tuning an audio system.  When compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum (below 60Hz and above 16 KHz).  HouseCurve compensates for this by applying a moderate boost.  See [internal compensation](../manual/measure_setup.md#internal-mic-compensation) for more information.

If measurements don't look right, try using a [different internal mic](../manual/measure_setup.md#internal-mic-location) or removing the case.  On new devices the mics should measure about the same.

## External Microphones

HouseCurve will automatically use an external mic if one is plugged in (provided that [external mics are enabled](../manual/measure_setup.md#external-mic-enable)).  The [setup status](../manual/plots.html#setup-status) will display the name of the microphone.   If the microphone is not detected, check cables and verify the microphone is working by recording audio with the Voice Memo iOS application.

HouseCurve has been tested with the following external microphones:

* [miniDSP UMIK-1](https://www.minidsp.com/products/acoustic-measurement/umik-1) connected with this [Lightning to USB adapter](https://www.apple.com/shop/product/MD821AM/A/lightning-to-usb-camera-adapter)
* [Dayton Audio iMM-6](https://www.daytonaudio.com/product/1117/imm-6-idevice-calibrated-measurement-microphone) connected with this [Lightning to 3.5 mm adapter](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jackadapter)

HouseCurve supports the following [curve file format](../manual/file_formats.md#curves) for microphone calibration.

If you are getting strange measurements, try another microphone.  The [iPhone EarPods](https://www.apple.com/shop/product/MMTN2AM/A/earpods-with-lightning-connector) buried in your desk drawer are great for testing adapters, cables, etc.  You can also compare to the internal mics.


## CarPlay

When CarPlay is used to connect to an automobile audio system, be aware that the selected microphone will be the automobile (head unit) microphone, not the iPhone/iPad microphone.  It may be possible to override this by connecting an external microphone to the automobile.  Alternatively, connect using Bluetooth or the headphone connector.


