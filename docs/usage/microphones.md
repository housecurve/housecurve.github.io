---
layout: default

title: Microphones
parent: Usage
nav_order: 2
---

# Microphones
HouseCurve will default to using the built in microphone of your iPhone/iPad.  These microphones have a surprisingly flat response and are quite acceptable for tuning an audio system.  When compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum (below 60Hz and above 16 KHz).  HouseCurve compensates for this by applying a moderate boost.  See [internal compensation](../manual/measure_setup.md#internal-mic-compensation) for more information.

For additional accuracy, HouseCurve can use external microphones.  It will automatically use an external microphone if one is connected to your iPhone/iPad.  HouseCurve has been tested with the following external microphones:

* [miniDSP UMIK-1](https://www.minidsp.com/products/acoustic-measurement/umik-1)
* [Dayton Audio iMM-6](https://www.daytonaudio.com/product/1117/imm-6-idevice-calibrated-measurement-microphone)

HouseCurve uses the following [curve file format](../manual/file_formats.md#curves) for microphone calibration.

When CarPlay is used to connect to an automobile audio system, be aware that the selected microphone will be the automobile (head unit) microphone, not the iPhone/iPad microphone.  It may be possible to override this by connecting an external microphone to the automobile.  Alternatively, connect using Bluetooth or the headphone connector.

If you are getting strange measurements, try another microphone.  A common microphone for sanity checks is the [iPhone EarPods with Lighning Connector](https://www.apple.com/shop/product/MMTN2AM/A/earpods-with-lightning-connector).


