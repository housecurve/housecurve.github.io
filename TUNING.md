## How to tune an audio system
{:.no_toc}

1. table of contents inserted here
{:toc}

### Tuning overview
The process for tuning an audio system will generally involve the tasks described below:

[Target curve](#target-curve).  The target curve defines how the audio system will sound.  The choice of curve is subject to personal taste.

[Apply equalization](#apply-equalization).  Equalization means adjusting the volume level at different frequencies to match the target curve.

For audio systems with separately adjustable speakers, such as a 2.1 system (main speakers and a subwoofer), the following steps should be performed **before equalization**:

[Match speaker levels](#match-speaker-levels).  The speakers of the audio system should be playing at roughly the same volume level in the listening area.  This is done to ensure measurements will reflect the whole audio system and also to avoid using equalization to correct level differences.

[Choose crossover frequencies](#choose-crossover-frequencies).  Crossover frequencies are used to define regions of responsibility for speakers.  This is important when using speakers that have a limited frequency range, such as a subwoofer.

[Time align speakers](#time-align-speakers).  When two speakers produce the same sound, time alignment ensures the sound arrives at the listening area at the same time.  When speakers are not time aligned, they will interfere with each other in ways that cannot be corrected by equalization.

It may be necessary to iterate over these tasks a few times to get things right.  Experimentation is encouraged to find what works for a given audio system.


### Target curve
A Target Curve, or “house curve”, is a visual guide to ensure you tune your audio system in the right direction.  The system is "tuned" when the average  measurement matches the Target Curve.

HouseCurve provides some common curves to experiment with.  These can be selected by going to [Plot Setup](MANUAL.md/plot-setup).  The "House" curves are flatter and intended for home listening.  The "Car" curves have significantly more bass which is common for automobile listing.  HouseCurve will display the selected curve on the magnitude plot when there are measurements.

![target curve](/assets/img/target_curve.png "Measurement compared to B&K target curve (yellow)")

The choice of Target Curve is subject to individual taste.  Typically, listeners prefer it when low frequencies are louder than high frequencies.  A  downward slope of 1 dB/octave is quite common.  Ultimately, your ears will tell you what one is best.

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

The curve that works best with your audio system will somewhat depend on how the system is measured (mic type, mic placement, mic direction, etc).  When adjusting a single system this doesn't really matter so long as you perform measurements consistently - the curve is just a guide.  However, if you are applying the same curve to multiple audio systems, be aware that the same measurement technique needs to be applied for consistent results.

### Apply equalization

If the audio system has separately adjustable speakers, such as a subwoofer, ensure that levels have been [matched](#match-speaker-levels), crossovers are [selected](#choose-crossover-frequencies) and speakers are [time aligned](#time-align-speakers).

Equalization in general means changing the volume level at different frequencies.  There are many ways an audio system can be changed to make this happen.  What can be changed depends on the audio system:

* Change speaker position in room
* Adjust the bass or treble controls
* Change relative levels of speakers (ex: subwoofer level)
* Adjust the graphic or parametric equalizer settings
* Change the room (ex: sound dampening, adjust furniture)

When equalizing, the goal is to adjust the audio system such that the average magnitude measurement ends up within the +/- 3 dB band that surrounds the Target Curve.

![equalization start](/assets/img/equalizer_start.png "Adjust until measurement within target curve band")

Adjust the audio system in small steps, collecting the same measurements after each change.  [Saved measurements](/MANUAL.md#saved-measurement) are helpful for seeing the effect of an adjustment as can be seen below:

![equalization changed](/assets/img/equalizer_changed.png "Save measurements to see what adjustment did")

When most of the average magnitude measurement is within the target band, the audio system is sufficiently equalized.  Further adjustments may not be perceptible.

Avoid adjustments that are beyond the capability of the audio system.  Doing so will lead to distortion and possibly audio system damage.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more signal power.  A change of +20 dB is 100 times more signal power!


### Match speaker levels
For systems with separately adjustable speakers, the relative levels need to be matched.  This is done to reduce the amount of equalization required.   Adjust the speaker levels such that measurements in the listening area are roughly close to the target curve on the magnitude plot.

Make sure all speakers are active and set the overall audio system volume to a normal listening level.  It can be helpful to set HouseCurve’s [Display Mode](/MANUAL.md#display-mode) to History.

Take a measurement from the middle of the listening area.  On the magnitude plot, observe how the measurement lines up with the Target Curve.  Adjust individual speaker levels and repeat the measurement as needed to get close to the Target Curve.

The example below shows an audio system consisting of main speakers and a subwoofer.  The subwoofer level was initially too low.  It was adjusted a few times to get close enough to the Target Curve.

![subwoofer level change](/assets/img/subwoofer_level_change.png "Matching subwoofer level to main speakers")


### Choose crossover frequencies

For audio systems that incorporate limited range speakers, the crossover frequencies need to be selected.

The classic approach is to select crossover frequencies based on speaker specifications, but these may not reflect how the speakers perform in the room.  It is better to measure the actual speaker performance. Use [saved measurements](/MANUAL.md#saved-measurments), to compare individual speaker measurements and select a crossover frequency.

The screenshot below shows a 2.1 desktop audio system consisting of [main speakers](https://www.kantoaudio.com/powered-speakers/yu2) and a [subwoofer](https://www.kantoaudio.com/subwoofers/sub6).  The speakers were measured separately with crossovers disabled and no equalization.  The [subwoofer was measured](/USAGE.md#subwoofer-measurements) first and saved (grey), then the main speakers were measured (green).

![finding crossover frequency](/assets/img/finding_crossover_frequency_kanto_yu2.png "Measure speakers separately to find best crossover frequency")

The published frequency range for the main speakers is 80-20000 Hz and the subwoofer is 35-165 Hz.  Based on the specs, the overlap of these speakers is 80 - 165 Hz and the crossover frequency should be somewhere in that range.

On the magnitude plot, we can see the main speaker drops off quickly below ~120 Hz.  For this system the crossover frequency should be somewhere in the 100-120 Hz range.  The subwoofer is more than capable of filling in below 100 Hz.


### Time align speakers

When an audio system contains limited range speakers (subwoofers, bi-amped speakers, etc) time alignment becomes an important adjustment.

HouseCurve supports two methods of time aligning speakers.  The [magnitude method](#time-align-using-magnitude) and the [phase method](#time-align-using-phase).  The magnitude method is simpler, the phase method can be more accurate.

#### What is time alignment? ####

At the crossover frequencies of an audio system, sound transitions from one speaker to another.  In this region, speakers on either side of the crossover are active.  If sound leaves the speakers at different times, [destructive interference](https://www.phys.uconn.edu/~gibson/Notes/Section5_2/Sec5_2.htm) (or “cancellation”) can occur leading to audible dips in the sound level at the crossover frequency.  These dips cannot be fixed by equalization.

The degree of time alignment needed is dependent on the wavelength of the crossover frequency (wavelength = 1 / frequency).  Destructive interference reaches a maximum when there is a half wavelength of delay between speakers.  For example, a subwoofer and a main speaker are separated by a crossover at 100 Hz.  The wavelength at 100 Hz is 0.01 seconds or 10 milliseconds (ms).  If the subwoofer is delayed by half a wavelength, or 5 ms, then peak destructive interference will occur.  The effect will subside for smaller or larger delays, ex: 0-2 ms or 8-10 ms.  

Since sound is a wave, the pattern of destructive interference will repeat at multiples of the crossover wavelength.  In the example above, peak destructive interference will happen for delays of 5 ms, 15 ms, 25 ms and so on.  This makes time alignment tricky as it’s possible to align on the wrong cycle and have more delay than needed.

The adjustments available for time alignment depend on the audio system:  

* Speaker location can be adjusted to add/remove delay (sound takes about 3 ms to travel 1 meter)
* Amplifiers/receivers typically have delay or distance settings.
* Active crossovers and parametric equalizers usually have delay settings too (a [MiniDSP 2x4 HD](https://www.minidsp.com/products/minidsp-in-a-box/minidsp-2x4-hd) was used for many of the measurements in this document).
* Subwoofers may have a polarity switch (often labelled “phase”) or a dial that permits adjusting phase from 0 to 180 degrees.

Most audio systems will have a combination of these adjustments and **experimentation will be required** to figure out what works best.


#### Time align using magnitude
Destructive interference will cause a dip in the magnitude measurement at the crossover frequency.  We can use this effect to figure out what adjustments increase or decrease the dip (polarity, phase, delay, distance, whatever you have).  The speakers are time aligned for the adjustment with the smallest dip.

When using this method it’s important to avoid changing audio system levels (volume, bass/treble, equalizer, etc).

Ensure speakers on either side of the crossover are enabled.  Set HouseCurve’s Display Mode to [History](/MANUAL.md#display-mode).  Zoom into the region around the crossover frequency.  It is also best to set the [Target Curve Fit](/MANUAL.md#target-curve-fit) to manual and select an appropriate level as this will prevent the target curve from moving as adjustments are made.

Take a measurement from the middle of the listening area.  On the magnitude plot, place the cursor at the crossover frequency and observe the magnitude value.  Adjust the audio system.  Repeat the measurement and observe the new magnitude value.  Continue to make adjustments until the maximum magnitude level is achieved and the dip is the smallest.  The plot below shows a system being adjusted from the worst alignment (largest dip) to the best (smallest dip).

![subwoofer align magnitude](/assets/img/subwoofer_align_magnitude.png "Adjust until the smallest dip is found")

The downfall of this approach is that maximum magnitude can be achieved at multiples of the crossover wavelength.  This can lead to tuning the system with more delay than necessary.  The group delay plot can be used to check this for subwoofers.  If there is a significant change in group delay before or after the crossover, this could indicate too much delay.  This can be seen in the group delay plot below.

![subwoofer align groupdelay](/assets/img/subwoofer_align_group_delay.png "Check subwoofer alignment with group delay")


#### Time align using phase

When two speakers are time aligned, they will have the same phase at the crossover frequency and their phase plots will have the same slope in the crossover region.

Time alignment using phase requires **separate measurement** of the speakers on either side of the crossover.  To do this with HouseCurve, measurements of the first speaker are compared to the second using a [saved measurement](/MANUAL.md#saved-measurement).  The second speaker is adjusted until a good time alignment is found on the phase plot.

Phase measurements are very sensitive to changes in the distance between speaker and microphone.  For best results, take measurements from the middle of the listening area, keeping the microphone in the same location for each measurement.  For lower frequency crossovers (~100 Hz), it is possible to average phase measurements in the listening area, but this will quickly break down for large areas.  Keep in mind that sound takes about 3 ms to travel 1 meter.

Phase measurements must share the same time reference to be compared.  To achieve this with HouseCurve, the chirp sound must come from the same speaker (for more information, see [measurement process](/USAGE.md#measurement-process)).

For a typical 2.1 audio system, use **either** the left or right main speaker as the “chirp” speaker.  Use the same chirp speaker for both subwoofer and main speaker measurements.  Measure the main speakers first, allowing the sweep to play from both left and right speakers to get an average phase.  Save this measurement.  [Measure the subwoofer](/USAGE.md#subwoofer-measurements) second and compare to the saved main measurement.  Adjust the audio system as needed to obtain alignment (adjust main speakers or subwoofer).

The phase plot below shows a 2.1 audio system with good time alignment.  The subwoofer measurement (green) is compared to a saved measurement of the main speakers (grey).  The crossover frequency is 100 Hz.  The main speakers and subwoofer have nearly the same phase at the crossover frequency, and the phase slopes are roughly the same.

![subwoofer align phase](/assets/img/subwoofer_align_phase.png "Phase plot showing subwoofer aligned with main speakers")

The plot below shows the same audio system in various states of alignment.  As delay is changed, the phase of the subwoofer moves up or down at the crossover frequency.  The slope of the phase will also slowly change with delay.

![subwoofer phase change](/assets/img/subwoofer_align_phase_change.png "Phase plot showing different delay adjustments")

Counterintuitively, the subwoofer phase measurements above (green) were generated by delaying the main speakers (grey).  This works because delaying the main speakers also delays the chirp sound which is the reference for the subwoofer phase.  Subwoofers tend to have more delay to begin with, so delaying the main speakers to match is often the correct adjustment.

Finally, in the plot below, the audio system is aligned with too much delay.  While the main speakers and subwoofer have the nearly same phase at the crossover frequency, the phase slopes are different.  This situation is sometimes described as “phase aligned but not time aligned”.  In this situation, try adding or subtracting delay equivalent to the crossover wavelength.

![subwoofer phase not time](/assets/img/subwoofer_align_phase_not_time.png "Phase aligned but not time aligned")

As with the [magnitude method](#time-align-using-magnitude) of time alignment, the group delay plot can be consulted to double check the alignment.  This requires taking a new measurement with both speakers active.

In the example plots above, the crossovers were disabled to ensure the measurements had enough signal on either side of the crossover to see the phase slope.  Use caution when measuring with crossovers disabled as this could lead to audio system damage.  An alternative approach is to disable [Coherence Blanking](/MANUAL.md#coherence-blanking).

The degree of success one will have with this method depends a lot on the audio system and the room.  Sometimes it is better to start with the magnitude method and fine tune using the phase method.


