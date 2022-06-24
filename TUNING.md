---
layout: default
nav_order: 6
---
# How to tune an audio system

## Tuning overview

The process for tuning an audio system will generally involve the tasks described below.  For audio systems with separately adjustable speakers, such as a 2.1 system (left, right, subwoofer), all the steps below should be performed.  If you have a simple 2.0 audio system (just a left and right speaker), you can skip ahead to choosing a target curve and applying equalization.  It may be necessary to experiment with different adjustments and to iterate over these steps a few times.

1. [Match speaker levels](#match-speaker-levels).  The speakers of the audio system should be playing at roughly the same volume level in the listening area.  This is done to ensure measurements will reflect the whole audio system and also to avoid using equalization to correct level differences.

1. [Choose crossover frequencies](#choose-crossover-frequencies).  Crossover frequencies are used to define regions of responsibility for speakers.  This is important when using speakers that have a limited frequency range, such as a subwoofer.

1. [Time align speakers](#time-align-speakers).  When two speakers produce the same sound, time alignment ensures the sound arrives at the listening area at the same time.  When speakers are not time aligned, they will interfere with each other in ways that cannot be corrected by equalization.

1. [Choose a target curve](#choose-target-curve).  The target curve defines how the audio system will sound.  The choice of curve is subject to personal taste.

1. [Apply equalization](#apply-equalization).  Equalization means adjusting the volume level at different frequencies to match the target curve.


## Match speaker levels

For systems with separately adjustable speakers, the relative levels need to be matched.  This is done to reduce the amount of equalization required.   Adjust the speaker levels such that measurements in the listening area are roughly close to the target curve on the magnitude plot.

Make sure all speakers are active and set the overall audio system volume to a normal listening level.  It can be helpful to set HouseCurve’s [Display Mode](/MANUAL.md#display-mode) to History.

Take a measurement from the middle of the listening area.  On the magnitude plot, observe how the measurement lines up with the Target Curve.  Adjust individual speaker levels and repeat the measurement as needed to get close to the Target Curve.

The example below shows an audio system consisting of main speakers and a subwoofer.  The subwoofer level was initially too low.  It was adjusted a few times to get close enough to the Target Curve.

![subwoofer level change](/assets/img/subwoofer_level_change.png "Matching subwoofer level to main speakers")


## Choose crossover frequencies

For audio systems that incorporate limited range speakers, the crossover frequencies need to be selected.

The classic approach is to select crossover frequencies based on speaker specifications, but these may not reflect how the speakers perform in the room.  It is better to measure the actual speaker performance. Use [saved measurements](/MANUAL.md#saved-measurments), to compare speakers and select a crossover frequency.

The screenshot below shows a 2.1 desktop audio system consisting of [main speakers](https://www.kantoaudio.com/powered-speakers/yu2) and a [subwoofer](https://www.kantoaudio.com/subwoofers/sub6).  The speakers were measured separately with crossovers disabled and no equalization.  The [subwoofer was measured](/USAGE.md#subwoofer-measurements) first and saved (grey), then the main speakers were measured (green).

![finding crossover frequency](/assets/img/crossover_select.png "Measure speakers separately to find best crossover frequency")

The published frequency range for the main speakers is 80-20000 Hz and the subwoofer is 35-165 Hz.  Based on the specs, the overlap of these speakers is 80 - 165 Hz and the crossover frequency should be somewhere in that range.

On the magnitude plot, we can see the main speaker drops off quickly below ~120 Hz.  For this system the crossover frequency should be somewhere in the 100-120 Hz range.  The subwoofer is more than capable of filling in below 100 Hz.


## Time align speakers

When an audio system contains limited range speakers (subwoofers, bi-amped speakers, etc) time alignment becomes an important adjustment.

HouseCurve supports two methods of time aligning speakers.  The [magnitude method](#time-align-using-magnitude) and the [phase method](#time-align-using-phase).  The magnitude method is simpler, the phase method can be more accurate.

### What is time alignment?

At the crossover frequencies of an audio system, sound transitions from one speaker to another.  In this region, speakers on either side of the crossover are active.  If sound leaves the speakers at different times, [destructive interference](https://www.phys.uconn.edu/~gibson/Notes/Section5_2/Sec5_2.htm) (or “cancellation”) can occur leading to audible dips in the sound level at the crossover frequency.  These dips cannot be fixed by equalization.

The degree of time alignment needed is dependent on the wavelength of the crossover frequency (wavelength = 1 / frequency).  Destructive interference reaches a maximum when there is a half wavelength of delay between speakers.  For example, a subwoofer and a main speaker are separated by a crossover at 100 Hz.  The wavelength at 100 Hz is 0.01 seconds or 10 milliseconds (ms).  If the subwoofer is delayed by half a wavelength, or 5 ms, then peak destructive interference will occur.  The effect will subside for smaller or larger delays, ex: 0-2 ms or 8-10 ms.  

Since sound is a wave, the pattern of destructive interference will repeat at multiples of the crossover wavelength.  In the example above, peak destructive interference will happen for delays of 5 ms, 15 ms, 25 ms and so on.  This makes time alignment tricky as it’s possible to align on the wrong cycle and have more delay than needed.

The adjustments available for time alignment depend on the audio system:  

* Speaker location can be adjusted to add/remove delay (sound takes about 3 ms to travel 1 meter)
* Amplifiers/receivers typically have delay or distance settings.
* Active crossovers and parametric equalizers usually have delay settings too (a [MiniDSP 2x4 HD](https://www.minidsp.com/products/minidsp-in-a-box/minidsp-2x4-hd) was used for many of the measurements in this document).
* Subwoofers may have a polarity switch (often labelled “phase”) or a dial that permits adjusting phase from 0 to 180 degrees.

Most audio systems will have a combination of these adjustments and **experimentation will be required** to figure out what works best.

### Time align using magnitude

Destructive interference will cause a dip in the magnitude measurement at the crossover frequency.  We can use this effect to figure out what adjustments increase or decrease the dip (polarity, phase, delay, distance, whatever you have).  The speakers are time aligned for the adjustment with the smallest dip.

When using this method it’s important to avoid changing audio system levels (volume, bass/treble, equalizer, etc).

Ensure speakers on either side of the crossover are enabled.  Set HouseCurve’s Display Mode to [History](/MANUAL.md#display-mode).  Zoom into the region around the crossover frequency.  It is also best to set the [Target Curve Fit](/MANUAL.md#target-curve-fit) to manual and select an appropriate level as this will prevent the target curve from moving as adjustments are made.

Take a measurement from the middle of the listening area.  On the magnitude plot, place the cursor at the crossover frequency and observe the magnitude value.  Adjust the audio system.  Repeat the measurement and observe the new magnitude value.  Continue to make adjustments until the maximum magnitude level is achieved and the dip is the smallest.  The plot below shows a system being adjusted from the worst alignment (largest dip) to the best (smallest dip).

![subwoofer align magnitude](/assets/img/subwoofer_align_magnitude.png "Adjust until the smallest dip is found")

The downfall of this approach is that maximum magnitude can be achieved at multiples of the crossover wavelength.  This can lead to tuning the system with more delay than necessary.  The group delay plot can be used to check for this.  Excess delay will appear as a step change in group delay before or after the crossover.  The group delay plot below shows a system with increasing amounts of subwoofer delay.  The system is initally aligned at 100 Hz (darkest green).  As unnecessary wavelengths of delay are added, the group delay increases (at 100 Hz, one wavelength is 10 ms).

![subwoofer align groupdelay](/assets/img/subwoofer_align_group_delay.png "Check subwoofer alignment with group delay")

### Time align using phase

When two speakers are time aligned, they will have the same phase at the crossover frequency and their phase plots will have the same slope in the crossover region.

Time alignment using phase requires **separate measurement** of the speakers on either side of the crossover.  To do this with HouseCurve, measurements of the first speaker are compared to the second using a [saved measurement](/MANUAL.md#saved-measurement).  The second speaker is adjusted until a good time alignment is found on the phase plot.

Phase measurements are very sensitive to changes in the distance between speaker and microphone.  For best results, take measurements from the middle of the listening area, keeping the microphone in the same location for each measurement.  For lower frequency crossovers (~100 Hz), it is possible to average phase measurements in the listening area, but this will quickly break down for large areas.  Keep in mind that sound takes about 3 ms to travel 1 meter.

Phase measurements must share the same time reference to be compared.  To achieve this with HouseCurve, the chirp sound must come from the same speaker (for more information, see [measurement process](/USAGE.md#measurement-process)).

For a typical 2.1 audio system, use **either** the left or right main speaker as the “chirp” speaker.  Use the same chirp speaker for both subwoofer and main speaker measurements.  Measure the main speakers first, allowing the sweep to play from both left and right speakers to get an average phase.  Save this measurement.  [Measure the subwoofer](/USAGE.md#subwoofer-measurements) second and compare to the saved main measurement.  Adjust the audio system as needed to obtain alignment (adjust main speakers or subwoofer).

The phase plot below shows a 2.1 audio system with good time alignment.  The subwoofer measurement (green) is compared to a saved measurement of the main speakers (grey).  The crossover frequency is 100 Hz.  The main speakers and subwoofer have nearly the same phase at the crossover frequency, and the phase slopes are roughly the same.

![subwoofer align phase](/assets/img/subwoofer_align_phase.png "Phase plot showing subwoofer aligned with main speakers")

The plot below shows the same audio system in various states of alignment.  As delay is changed, the phase of the subwoofer moves up or down at the crossover frequency.  The overall slope of the phase will also change.

![subwoofer phase change](/assets/img/subwoofer_align_phase_change.png "Phase plot showing different delay adjustments")

Counterintuitively, the subwoofer phase measurements above (green) were generated by delaying the main speakers (grey).  This works because delaying the main speakers also delays the chirp sound which is the reference for the subwoofer phase.  Subwoofers tend to have more delay to begin with, so delaying the main speakers to match is often the correct adjustment.

Finally, in the plot below, the audio system is aligned, but on the wrong cycle (too much delay).  While the main speakers and subwoofer have the nearly same phase at the crossover frequency, the phase slopes are different.  This is sometimes described as “phase aligned but not time aligned”.  In this situation, try adding or subtracting a delay of one crossover wavelength (ex: 10 ms at 100 Hz).  With a subwoofer, you can also try inverting the polarity (aka "phase" switch).  This effectively changes the subwoofer's delay by 1/2 a wavelength, thus it is also necessary to add or subtract a delay of half a crossover wavelength (ex: 5 ms at 100 Hz).

![subwoofer phase not time](/assets/img/subwoofer_align_phase_not_time.png "Phase aligned but not time aligned")

As with the [magnitude method](#time-align-using-magnitude), the group delay plot can be consulted to double check the alignment.  This requires taking a new measurement with both speakers active.

In the example plots above, the crossovers were disabled to ensure the measurements had enough signal on either side of the crossover to see the phase slope.  Use caution when measuring with crossovers disabled as this could lead to audio system damage.  An alternative approach is to disable [Coherence Blanking](/MANUAL.md#coherence-blanking).

The degree of success one will have with this method depends a lot on the audio system and the room.  Sometimes it is better to start with the magnitude method and fine tune using the phase method.


## Choose Target curve

A Target Curve, or “house curve”, is a visual guide to ensure you tune your audio system in the right direction.  The system is "tuned" when the average  measurement matches the Target Curve.

HouseCurve provides some common curves to experiment with.  These can be selected by going to [Plot Setup](MANUAL.md#plot-setup-screen).  The "House" curves are flatter and intended for home listening.  The "Car" curves have significantly more bass which is common for automobile listing.  HouseCurve will display the selected curve on the magnitude plot when there are measurements.

![target curve](/assets/img/target_curve.png "Measurement compared to B&K target curve (yellow)")

The choice of Target Curve is subject to individual taste.  Typically, listeners prefer it when low frequencies are louder than high frequencies.  A  downward slope of 1 dB/octave is quite common.  Let your ears be the judge.

Custom curves can be created with a text editor and [imported](/MANUAL.md#target-curve) into HouseCurve.  See [curve file format](/USAGE.md#curve-file-format) for more information.  The curves provided by HouseCurve are a great starting point for making your own:

* [House A](/curves/House%20A.txt)
* [House B](/curves/House%20B.txt)
* [House C](/curves/House%20C.txt)
* [Car A](/curves/Car%20A.txt)
* [Car B](/curves/Car%20B.txt)
* [Car C](/curves/Car%20C.txt)

In the audiophile world, a “flat” response is often seen as the ultimate goal.  However, for everyday listening, a flat response tends to sound overly “bright” and unpleasant.  Try it for yourself: [Flat Target Curve](/curves/flat.txt).

Below are some resources for understanding what house curves do and how to choose them:
* [Advice on better house curve?](https://www.minidsp.com/forum/dirac-series-support/17523-advice-on-better-house-curve)
* [House Curve: What it is, why you need it, how to do it](https://www.hometheatershack.com/forums/rew-forum/96-house-curve-what-why-you-need-how-do.html)
* [Relevant loudspeaker tests, in studios, in Hi-Fi dealers' demo rooms, in the home etc](https://www.bksv.com/media/doc/17-197.pdf)
* [The Measurement and Calibration of Sound Reproducing Systems](http://www.aes.org/e-lib/browse.cfm?elib=17839)


## Apply equalization
If the audio system has separately adjustable speakers, such as a subwoofer, ensure that levels have been [matched](#match-speaker-levels), crossovers are [selected](#choose-crossover-frequencies) and speakers are [time aligned](#time-align-speakers).

### What is equalization?

Equalization means adjusting an audio system’s output such that the measured response in the listening area aligns with a target curve.  It can be used to compensate for characteristics of the audio system, or to correct for the effects of the room (aka “room correction”).  In practice, it's hard to separate the audio system from the room, so we end up adjusting for both.

When sound leaves an audio system, it interacts with the room, but this interaction changes with frequency.  Below the Schroeder frequency, or about 300 Hz, room resonances have a dominant impact on what is heard in the listening area.  At these frequencies, the room is in control.  Above the Schroeder frequency, direct sound from the audio system begins to dominate with contributions from room diffusion, absorption and reflection.  In this region, the audio system is mostly in control.  Thus, when equalizing a typical home or car audio system, we are correcting for the room below the Schroeder frequency and for the audio system above it (for an excellent deep dive, please read [Floyd Toole’s paper](https://www.harman.com/documents/AudioScience_0.pdf)).

When applying equalization, it is best to start at the low frequencies and work your way up.  At low frequencies, room resonances will create large peaks and dips in the magnitude.  These will be quite audible, so focus on smoothing them out to the target curve.  Moving toward higher frequencies, peaks and dips become much less audible and should not be adjusted.  Instead, shift your focus to adjusting wide regions of the magnitude response towards the target curve (an octave or more).  At the very upper end (10 KHz), it may not be worth making any adjustments at all (A great video on the topic is [here](https://www.youtube.com/watch?v=TwGd0aMn1wE)).

HouseCurve supports automatic and manual equalization:

- [Automatic equalization](#automatic-equalization), HouseCurve generates a set of filters to correct a measurement to a target curve.  If your audio system has a parametric equalizer, the filter parameters can be imported from a file, or manually entered.  Even without a parametric equalizer, the feature is still useful - you can see what HouseCurve would adjust and use that as a guide.

- [Manual equalization](#manual-equalization) is the most straight forward approach.  It works by iteratively measuring the audio system, adjusting it, then measuring again.  It will work with any audio system, even ones with limited adjustments (ex: you can move furniture and see the impact).

### Automatic Equalization

HouseCurve's automatic equalization tool generates filter settings for parametric equalizers.  It works by correcting a [saved measurement](MANUAL.md#saved-measurement) to a [target curve](MANUAL.md#target-curve).  It can be accessed from the more menu <img src="/assets/img/more.png" alt="More" width="15">.  For best results **average several measurements** from the listening area and then save.  Averaging provides HouseCurve with a better picture of how sound changes in the listening area.

The image below shows a saved measurement (grey) being corrected to the target curve (yellow).  The filters that perform the correction are shown in magenta.  The predicted magnitude response (when filters are applied) is shown in cyan.

![equalize screen](/assets/img/equalize_biquads.png "Equalize screen showing correction filters and predicted output")

HouseCurve allocates filters to regions with the largest deviation from the target curve, starting with lower frequencies and ignoring blanked regions (see [Coherence Blanking](/MANUAL.md#coherence-blanking)).  The algorithm’s behavior can be controlled by tapping <img src="/assets/img/setup.png" alt="Setup" width="15"> to display the [equalize setup screen](MANUAL.md#equalize-setup-screen).  Plot settings, such target curve fit and blanking threshold also impact the algorithm.  Changes are reflected immediately.

The predicted response should be reasonably close to real world measurements.  The screenshot below shows the same audio system after applying filters generated by HouseCurve (green) compared to the original measurement (grey).

![measurement after equalizing](/assets/img/equalize_measure_after.png "Measured results will be reasonably close to predicted")

HouseCurve uses a form of Infinite Impule Response (IIR) filter known as peaking biquad filter.  These are commonly used in graphic and parametric equalizers to boost or cut at various frequencies.  You can view the individual filters by tapping <img src="/assets/img/detail.png" alt="Detail" width="15"> to bring up the Filter Detail screen, shown below.  This screen can be used to manually enter filter settings into your audio system.

![filter detail screen](/assets/img/equalize_detail.png "Filter details can be imported into your parametric equalizer")

The filters can be [exported](MANUAL.md#filter-export-screen) to a file by tapping <img src="/assets/img/export.png" alt="Export" width="15">.  This file can then be imported into a compatible parametric equalizer, such as a [miniDSP 2x4HD](https://www.minidsp.com/products/minidsp-in-a-box/minidsp-2x4-hd), or software based equalizers like [Equalizer APO](https://sourceforge.net/projects/equalizerapo/).

HouseCurve's biquad filters are based on the [Audio EQ Cookbook by Robert Bristow-Johnson](https://www.w3.org/TR/audio-eq-cookbook/).  **Warning** the biquad coefficients exported by HouseCurve may not be compatible with your audio system.  As a precaution, turn the volume down on the first import just in case.  If you have questions or experience problems, please [reach out](mailto:support@housecurve.com).

### Manual Equalization

Equalization means changing the volume level at different frequencies.  There are many ways an audio system can be changed to make this happen:

* Change speaker position in room
* Adjust the bass or treble controls
* Change relative levels of speakers (ex: subwoofer level)
* Adjust the graphic or parametric equalizer settings
* Change the room (ex: sound dampening, adjust furniture)

When equalizing, the goal is to adjust the audio system such that the average magnitude measurement ends up within the +/- 3 dB band that surrounds the Target Curve.

![equalization start](/assets/img/equalizer_start.png "Adjust until measurement within target curve band")

Adjust the audio system in small steps, collecting the same measurements after each change.  [Saved measurements](/MANUAL.md#saved-measurement) are helpful for seeing the effect of an adjustment as can be seen below.  You can also take a look at the [Automatic Equalization](automatic-equalization) screen to see what HouseCurve would equalize (based on the saved measurement).

![equalization changed](/assets/img/equalizer_changed.png "Save measurements to see what adjustment did")

When most of the average magnitude measurement is within the target band, the audio system is sufficiently equalized.  Further adjustments may not be perceptible.

Avoid adjustments that are beyond the capability of the audio system.  Doing so will lead to distortion and possibly audio system damage.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more signal power.  A change of +20 dB is 100 times more signal power!

