---
layout: default

title: Measure Setup
parent: Manual
nav_order: 5
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
Use a logarithmic sinusoid sweep as the stimulus signal.  This is the default mode.  It requires a connection to the audio system in order to play the test signal.

### Pink Noise
Pink noise stimulus is provided for interest sake.  Measurements based on pink noise will have a signal to noise ratio that is lower than sine sweeps.  The measurement process is identical to sine sweep (this is not a real time analyzer (RTA) mode).

HouseCurve uses coherent averaging.  This has an interesting effect on Pink Noise measurements.  In a sonically treated room, such as one with sound absorbing panels on the walls, Pink Noise noise measurements will closely match Sine Sweep measurements.  In a more typical “reflective” room, Pink Noise magnitude measurements tend to be lower above ~2 KHz.  The degree to which the Pink Noise and Sine Sweep measurements match is an indication of how “dead” the room is.

### External Sine Sweep
This mode also uses a logarithmic sinusoid sweep, but it does not require a connection to the audio system.  Instead, the test signal must be manually transferred to the audio system (ex: SD card, CD, streaming library).  The audio system is responsible for playing the test signal and HouseCurve will listen for it when measure is tapped.

The test signal can be exported to a WAV file when this mode is selected.  The chirp and sweep channel setting will be used to produce the test signal file.

## Internal Mic Compensation
The built in iPhone/iPad microphones have a reasonably flat response and are quite acceptable for tuning an audio system.  However, when compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum.  

Internal Mic Compensation applies a moderate boost below 60 Hz and above 16 KHz to measurements made with the built in iPhone/iPad microphone.

## External Mic Calibration
HouseCurve supports calibrated external microphones.  Available calibrations will be displayed in the list.  Select None to disable calibration.

Microphone calibrations can be loaded tapping + at the top of the External Mic Calibration screen.  Calibrations can be removed by tapping Edit.

HouseCurve supports the following [Curve file format](../usage/file_formats.md#curve-file-format).




