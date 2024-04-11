---
layout: default

title: Measure Setup
parent: Manual
nav_order: 6
---

# Measure Setup
The Measure Setup screen can be accessed by tapping <img src="/assets/img/setup.png" alt="Setup" class="app-icon"> on the Measure screen.

![Measure setup screen](/assets/img/measure_setup.png)
{: .app-portrait-right }

## Chirp and Sweep Channel
The "chirp" and "sweep" sounds of the test signal can be played on different channels (see [measurement process](../usage/measurement_process.md)).  This is mainly used for [subwoofer measurements](../usage/subwoofer.md).


## Stimulus Type
Stimulus Type controls the "sweep" portion of the test signal (chirp + sweep) used to measure the audio system.

### Sine Sweep
Use a logarithmic sinusoid sweep.  This is the default mode.  It requires a connection to the audio system in order to play the test signal.

### External Sine Sweep
Play the test signal manually.  Use this when connection to the audio system isn't possible, or wireless methods are not working correctly.  The audio system is responsible for playing the test signal and HouseCurve will listen for it when measure is tapped.

When this mode is selected, the test signal can be exported to a [WAV file](file_formats.md#test-signal).

For more information, see [connecting](../usage/connecting.md#externally-played-sweeps).

### Pink Noise
Pink noise stimulus is provided for interest sake.  Measurements based on pink noise will have a signal to noise ratio that is lower than sine sweeps.  The measurement process is identical to sine sweep (this is not a real time analyzer (RTA) mode).

HouseCurve uses coherent averaging when collecting the measurement.  This has an interesting effect on Pink Noise measurements.  In a sonically treated room, such as one with sound absorbing panels on the walls, Pink Noise noise measurements will closely match Sine Sweep measurements.  In a more typical “reflective” room, Pink Noise magnitude measurements tend to be lower above ~2 KHz.  The degree to which the Pink Noise and Sine Sweep measurements match is an indication of how “dead” the room is.


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


