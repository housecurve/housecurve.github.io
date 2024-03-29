---
layout: default

title: Measurement Process
parent: Usage
nav_order: 4
---


# Measurement process
The measurement process starts when [<img src="/assets/img/measure.png" alt="Measure" class="app-icon">](../manual/measure_screen.md#measure) is tapped.  HouseCurve listens to the audio system play a test signal.  This signal consists of a “chirp” sound followed by a “sweep” sound.  The chirp is a timing reference that tells HouseCurve when to expect the sweep sound.  The sweep sound is used to measure the audio system.

The stages of the measurement process are displayed in the [Measurement Status](../manual/plots.md#measurement-status) area at the top of the screen.

![listening](/assets/img/measurement_listening.png "Tap measure to start measurement process")

When a measurement succeeds it will be displayed on the plots as shown below. 

![successful measurement](/assets/img/measurement_success.png "When measurement succeeds, it is displayed")


# Measurement failures
HouseCurve will abort the measurement process for the following reasons:

## Could not detect test signal
If HouseCurve is unable to detect the [chirp](#measurement-process) signal after about 10 seconds, it will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the chirp, but it does not need to be loud.
* Ensure that the audio system isn't buffering or cross fading the signal.  This can cause the chirp to be cut off or substantially distorted, see [connecting](connecting.md).
* If you can hear the chirp sound, check that the microphone is not obstructed.  Cases for iPhone/iPads can obstruct the microphone.  Be sure to aim the microphone at the audio system and ensure it’s not covered up by your hand (ex: Bottom of iPhone).
* If using an external microphone, ensure the cabling is connected properly.  Check that microphone is working by recording audio using the Voice Memo appplication.
* Try [externally played sweeps](https://housecurve.com/docs/usage/connecting.html#externally-played-sweeps) instead of wireless/wired connections.  Playing the test signal on repeat may help with buffering issues.

## Low measurement coherence
After the chirp is detected, HouseCurve records the [sweep](#measurement-process) as it is played by the audio system.  If the recorded sweep has a very low signal to noise ratio, HouseCurve will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the sweep, but it does not need to be loud.
* Take steps to reduce background noise.  HouseCurve works best when measurements are taken from a quiet listening area.
* Lower the [Coherence Blanking](../manual/plot_setup.md#coherence-blanking) threshold.



