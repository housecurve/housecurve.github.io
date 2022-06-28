---
layout: default

title: Measurement Process
parent: Usage
nav_order: 4
---


## Measurement process
A single measurement represents how the audio system sounds at a single location.  To get a realistic measurement of the listening area, it is important to **average measurements from several locations**.  Averaging will cancel small variances making it possible to find a “best fit” tune for a given listening area.  For a desk (near field), try measuring from 2-3 locations.  For a living room, try 3-5 locations.

The measurement process starts when [<img src="/assets/img/measure.png" alt="Measure" class="app-icon">](../manual/measure_screen.md#measure) is tapped.  HouseCurve listens to the audio system play a test signal.  This signal consists of a “chirp” sound followed by the stimulus “sweep” sound.  The chirp is a timing reference that tells HouseCurve when to expect the sweep sound.  The sweep sound is used to measure the audio system.

The stages of the measurement process are displayed in the [Measurement Status](../manual/plot_area.md#measurement-status) area at the top of the screen.

![listening](/assets/img/measurement_listening.png "Press measure to start measurement process")

When a measurement succeeds it will be displayed on the plots as shown below. 

![successful measurement](/assets/img/measurement_success.png "When measurement succeeds, it is displayed")

HouseCurve will abort the measurement process for the following reasons:

### Could not detect test signal
If HouseCurve is unable to detect the chirp signal after about 10 seconds, it will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the chirp, but it does not need to be loud.
* If you can hear the chirp sound, check that the microphone is not obstructed.  Cases for iPhone/iPads can obstruct the microphone.  Be sure to aim the microphone at the audio system and ensure it’s not covered up by your hand (ex: Bottom of iPhone).
* If using an external microphone, ensure the cabling is connected properly.  To rule out problems with the audio system, try measurements using the built-in microphone.

### Low measurement coherence
After the chirp is detected, HouseCurve records the sweep as it is played by the audio system.  If the recorded sweep has a very low signal to noise ratio, HouseCurve will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the sweep, but it does not need to be loud.
* Take steps to reduce background noise.  HouseCurve works best when measurements are taken from a quiet listening area.
* Lower the [Coherence Blanking](../manual/plot_setup.md#coherence-blanking) threshold.



