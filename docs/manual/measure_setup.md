---
layout: default

title: Measure Setup
parent: Manual
nav_order: 9
---

# Measure Setup
The Measure Setup screen can be accessed by tapping <img src="/assets/img/setup.png" alt="Setup" class="app-icon"> on the Measure screen.

![Measure setup screen](/assets/img/measure_setup.png)
{: .app-portrait-right }

## Chirp and Sweep Channel
The "chirp" and "sweep" sounds of the test signal can be played on different channels (see [measurement process](../usage/measurement_process.md)).  This is mainly used for [subwoofer measurements](../usage/subwoofer.md).

## External Stimulus
When enabled, HouseCurve will not attempt to play the test signal, it will only listen when measure is tapped.  Use this when connection to the audio system isn't possible, or wireless methods are not working correctly.

The test signal for the measurement tool can be exported to a [WAV file](file_formats.md#test-signal).  Channel settings for the measure tool are used to generate the file.

For more information, see [connecting](../usage/connecting.md#external-stimulus).

## Remove Delay
When measuring, HouseCurve expects the sweep sound to arrive at a precise moment after it detects the chirp.  Any difference between the expected and actual arrival will appear as a change in phase slope and a vertical shift in group delay.  This setting removes the difference by aligning the measured impulse response peak to t=0.

When averaging measurements, this setting should be enabled.  This ensures the average is not corrupted by delays a listener cannot experience, for example, listening from two different seats at the same time.

When time aligning speakers, this setting should be disabled.  The change in phase slope and group delay is needed to measure alignment.


## Volume Warning
If the iPhone/iPad volume is set too high when a measurement is started, a warning appears and the measurement is aborted.  The warning will only appear once per connection.  It can be disabled if it's a nuisance (ex: audio system has another way to control the volume).


## Internal Mic Location
Choose which internal microphone to use for measurement.  By default, HouseCurve uses the bottom microphone on iPhones and the top microphone on iPads.


## Internal Mic Compensation
The average built in iPhone/iPad microphone is reasonably flat, but begins to roll off below ~60 Hz.  Internal Mic Compensation brings the measured response closer to what you would get with a calibrated external mic.  It is worth keeping in mind that the iPhone/iPad can still "hear" below 60 Hz, it is just not as sensitive.


## External Mic Calibration
HouseCurve supports calibrated external microphones.  Available calibrations will be displayed in the list.  Choose "None" to disable calibration.

Microphone calibrations can be loaded tapping + at the top of the External Mic Calibration screen.  Calibrations can be removed by tapping Select.

HouseCurve uses the following [curve file format](file_formats.md#curves) for microphone calibration.


## External Mic Enable
HouseCurve will use an external microphone if one is connected to the iPhone / iPad.  Disable this option to force HouseCurve to use the internal microphone.

This is useful when connected to USB devices (ex: DACs) that appear as input and output to the iPhone / iPad.


