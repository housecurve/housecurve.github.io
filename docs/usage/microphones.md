---
layout: default

title: Microphones
parent: Usage
nav_order: 2
---

# Microphones
HouseCurve will default to using the built in microphone of your iPhone/iPad.  These microphones have a surprisingly flat response and are quite acceptable for tuning an audio system.  When compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum (below 60Hz and above 16 KHz).  HouseCurve compensates for this by applying a moderate boost.  See [internal compensation](../manual/measure_setup.md#internal-mic-compensation) for more information.


## External Microphones

For additional accuracy, HouseCurve can use external microphones.  Your iPhone/iPad will automatically detect when one is plugged in and tell HouseCurve to use it.  The [setup status](../manual/plots.html#setup-status) will indicate "external microphone".  If the microphone is not detected, check cables and verify the microphone is working by recording audio with the Voice Memo application.

HouseCurve has been tested with the following external microphones:

* [miniDSP UMIK-1](https://www.minidsp.com/products/acoustic-measurement/umik-1) connected with this [Lightning to USB adapter](https://www.apple.com/shop/product/MD821AM/A/lightning-to-usb-camera-adapter)
* [Dayton Audio iMM-6](https://www.daytonaudio.com/product/1117/imm-6-idevice-calibrated-measurement-microphone) connected with this [Lightning to 3.5 mm adapter](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jackadapter)

HouseCurve supports the following [curve file format](../manual/file_formats.md#curves) for microphone calibration.

If you are getting strange measurements, try another microphone.  The [iPhone EarPods](https://www.apple.com/shop/product/MMTN2AM/A/earpods-with-lightning-connector) buried in your desk drawer are great for testing adapters, cables, etc.


## CarPlay

When CarPlay is used to connect to an automobile audio system, be aware that the selected microphone will be the automobile (head unit) microphone, not the iPhone/iPad microphone.  It may be possible to override this by connecting an external microphone to the automobile.  Alternatively, connect using Bluetooth or the headphone connector.


