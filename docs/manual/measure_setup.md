---
layout: default

title: Measure Setup
parent: Manual
nav_order: 4
---

## Measure Setup Screen

### Chirp and Sweep Channel
The "chirp" and "sweep" sounds of the test signal can be played on different channels (see [measurement process](../usage/measurement_process.md)).  This is mainly used for [subwoofer measurements](../usage/subwoofer.md).

### Stimulus Type
Stimulus Type controls the test signal used to measure the audio system.

In most cases, the **Sine Sweep** should be used as it will produce measurements with a higher signal to noise ratio.  In this mode, HouseCurve requires a connection to the audio system in order to play the test signal.

**External Sine Sweep** mode does not require a connection to the audio system.  Instead, the test signal must be manually transferred to the audio system (ex: using an SD card).  During the measurement process, the audio system is responsible for playing the test signal and HouseCurve listens for it.

The test signal can be exported to a WAV file when this mode is selected.  Note - chirp and sweep channel setting will be used to produce the test signal file.

**Pink Noise** is provided for interest sake.  Measurements based on pink noise will have a lower signal to noise ratio.

HouseCurve uses coherent averaging.  This has an interesting effect on Pink Noise measurements.  In a sonically treated room, such as one with sound absorbing panels on the walls, Pink Noise noise measurements will closely match Sine Sweep measurements.  In a more typical “reflective” room, Pink Noise magnitude measurements tend to be lower above ~2 KHz.  The degree to which the Pink Noise and Sine Sweep measurements match is an indication of how “dead” the room is.

### Internal Mic Compensation
The built in iPhone/iPad microphones have a reasonably flat response and are quite acceptable for tuning an audio system.  However, when compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum.  

Internal Mic Compensation applies a moderate boost below 60 Hz and above 16 KHz to measurements made with the built in iPhone/iPad microphone.

### External Mic Calibration
HouseCurve supports calibrated external microphones.  Available calibrations will be displayed in the list.  Select None to disable calibration.

Microphone calibrations can be loaded tapping + at the top of the External Mic Calibration screen.  Calibrations can be removed by tapping Edit.

HouseCurve supports the following [Curve file format](../usage/file_formats.md#curve-file-format).




