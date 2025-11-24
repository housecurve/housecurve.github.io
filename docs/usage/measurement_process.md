---
layout: default

title: Measurement Process
parent: Usage
nav_order: 3
---


# Measurement process
The measurement process starts when <img src="/assets/img/measure.png" alt="Measure" class="app-icon"> is tapped.  HouseCurve will listen for the audio system to play the test signal.

The [Sweep](../manual/sweep.md) tool uses a test signal that consists of a “chirp” sound followed by a “sweep” sound.  The chirp is a timing reference that that signals when to expect the sweep.  If the tool doesn't hear the chirp, it will not measure the audio system.

The [Real Time](../manual/realtime.md) tool uses a pink noise test signal. There is no timing chirp because the tool only measures magnitude.  It will begin measurement immediately.

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
* Try [external stimulus](https://housecurve.com/docs/usage/connecting.html#external-stimulus) instead of wireless/wired connections.  Playing the test signal on repeat may help with buffering issues.

## Low measurement coherence
After the chirp is detected, HouseCurve records the [sweep](#measurement-process) as it is played by the audio system.  If the recorded sweep has a very low signal to noise ratio, HouseCurve will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the sweep, but it does not need to be loud.
* Take steps to reduce background noise.  HouseCurve works best when measurements are taken from a quiet listening area.
* Lower the [Coherence Blanking](../manual/plot_setup.md#coherence-blanking) threshold.



