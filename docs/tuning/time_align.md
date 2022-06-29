---
layout: default

title: Time Alignment
parent: Tuning
nav_order: 4
---


# Time align speakers

When an audio system contains limited range speakers (subwoofers, bi-amped speakers, etc) time alignment becomes an important adjustment.

## What is time alignment?

At the crossover frequencies of an audio system, sound transitions from one speaker to another.  In this region, speakers on either side of the crossover are active.  If sound leaves the speakers at different times, [destructive interference](https://www.phys.uconn.edu/~gibson/Notes/Section5_2/Sec5_2.htm) (or “cancellation”) can occur leading to audible dips in the sound level at the crossover frequency.  These dips cannot be fixed by equalization.

The degree of time alignment needed is dependent on the wavelength of the crossover frequency (wavelength = 1 / frequency).  Destructive interference reaches a maximum when there is a half wavelength of delay between speakers.  For example, a subwoofer and a main speaker are separated by a crossover at 100 Hz.  The wavelength at 100 Hz is 0.01 seconds or 10 milliseconds (ms).  If the subwoofer is delayed by half a wavelength, or 5 ms, then peak destructive interference will occur.  The effect will subside for smaller or larger delays, ex: 0-2 ms or 8-10 ms.  

Since sound is a wave, the pattern of destructive interference will repeat at multiples of the crossover wavelength.  In the example above, peak destructive interference will happen for delays of 5 ms, 15 ms, 25 ms and so on.  This makes time alignment tricky as it’s possible to align on the wrong cycle and have more delay than needed.

The adjustments available for time alignment depend on the audio system:  

* Speaker location can be adjusted to add/remove delay (sound takes about 3 ms to travel 1 meter)
* Amplifiers/receivers typically have delay or distance settings.
* Active crossovers and parametric equalizers usually have delay settings too (a [MiniDSP 2x4 HD](https://www.minidsp.com/products/minidsp-in-a-box/minidsp-2x4-hd) was used for many of the measurements in this document).
* Subwoofers may have a polarity switch (often labelled “phase”) or a dial that permits adjusting phase from 0 to 180 degrees.

Most audio systems will have a combination of these adjustments and **experimentation will be required** to figure out what works best.

HouseCurve supports two methods of time aligning speakers.

- [**Magnitude method**](#time-align-using-magnitude).  This is the simpler of the two methods, but it can be less accurate.

- [**Phase method**](#time-align-using-phase).  This method is more accurate, but it requires more steps to measure correctly.


## Time align using magnitude

Destructive interference will cause a dip in the magnitude measurement at the crossover frequency.  We can use this effect to figure out what adjustments increase or decrease the dip (polarity, phase, delay, distance, whatever you have).  The speakers are time aligned for the adjustment with the smallest dip.

When using this method it’s important to avoid changing audio system levels (volume, bass/treble, equalizer, etc).

Ensure speakers on either side of the crossover are enabled.  Set HouseCurve’s Display Mode to [History](../manual/plot_setup.md#display-mode).  Zoom into the region around the crossover frequency.  It is also best to set the [Target Curve Fit](../manual/plot_setup.md#target-curve-fit) to manual and select an appropriate level as this will prevent the target curve from moving as adjustments are made.

Take a measurement from the middle of the listening area.  On the magnitude plot, place the cursor at the crossover frequency and observe the magnitude value.  Adjust the audio system.  Repeat the measurement and observe the new magnitude value.  Continue to make adjustments until the maximum magnitude level is achieved and the dip is the smallest.  The plot below shows a system being adjusted from the worst alignment (largest dip) to the best (smallest dip).

![subwoofer align magnitude](/assets/img/subwoofer_align_magnitude.png "Adjust until the smallest dip is found")

The downfall of this approach is that maximum magnitude can be achieved at multiples of the crossover wavelength.  This can lead to tuning the system with more delay than necessary.  The group delay plot can be used to check for this.  Excess delay will appear as a step change in group delay before or after the crossover.  The group delay plot below shows a system with increasing amounts of subwoofer delay.  The system is initally aligned at 100 Hz (darkest green).  As unnecessary wavelengths of delay are added, the group delay increases (at 100 Hz, one wavelength is 10 ms).

![subwoofer align groupdelay](/assets/img/subwoofer_align_group_delay.png "Check subwoofer alignment with group delay")

## Time align using phase

When two speakers are time aligned, they will have the same phase at the crossover frequency and their phase plots will have the same slope in the crossover region.

Time alignment using phase requires **separate measurement** of the speakers on either side of the crossover.  To do this with HouseCurve, measurements of the first speaker are compared to the second using a [saved measurement](../manual/plot_setup.md#saved-measurement).  The second speaker is adjusted until a good time alignment is found on the phase plot.

Phase measurements are very sensitive to changes in the distance between speaker and microphone.  For best results, take measurements from the middle of the listening area, keeping the microphone in the same location for each measurement.  For lower frequency crossovers (~100 Hz), it is possible to average phase measurements in the listening area, but this will quickly break down for large areas.  Keep in mind that sound takes about 3 ms to travel 1 meter.

Phase measurements must share the same time reference to be compared.  To achieve this with HouseCurve, the chirp sound must come from the same speaker (for more information, see [measurement process](../usage/measurement_process.md)).

For a typical 2.1 audio system, use **either** the left or right main speaker as the “chirp” speaker.  Use the same chirp speaker for both subwoofer and main speaker measurements.  Measure the main speakers first, allowing the sweep to play from both left and right speakers to get an average phase.  Save this measurement.  [Measure the subwoofer](../usage/subwoofer.md) second and compare to the saved main measurement.  Adjust the audio system as needed to obtain alignment (adjust main speakers or subwoofer).

The phase plot below shows a 2.1 audio system with good time alignment.  The subwoofer measurement (green) is compared to a saved measurement of the main speakers (grey).  The crossover frequency is 100 Hz.  The main speakers and subwoofer have nearly the same phase at the crossover frequency, and the phase slopes are roughly the same.

![subwoofer align phase](/assets/img/subwoofer_align_phase.png "Phase plot showing subwoofer aligned with main speakers")

The plot below shows the same audio system in various states of alignment.  As delay is changed, the phase of the subwoofer moves up or down at the crossover frequency.  The overall slope of the phase will also change.

![subwoofer phase change](/assets/img/subwoofer_align_phase_change.png "Phase plot showing different delay adjustments")

Counterintuitively, the subwoofer phase measurements above (green) were generated by delaying the main speakers (grey).  This works because delaying the main speakers also delays the chirp sound which is the reference for the subwoofer phase.  Subwoofers tend to have more delay to begin with, so delaying the main speakers to match is often the correct adjustment.

Finally, in the plot below, the audio system is aligned, but on the wrong cycle (too much delay).  While the main speakers and subwoofer have the nearly same phase at the crossover frequency, the phase slopes are different.  This is sometimes described as “phase aligned but not time aligned”.  In this situation, try adding or subtracting a delay of one crossover wavelength (ex: 10 ms at 100 Hz).  With a subwoofer, you can also try inverting the polarity (aka "phase" switch).  This effectively changes the subwoofer's delay by 1/2 a wavelength, thus it is also necessary to add or subtract a delay of half a crossover wavelength (ex: 5 ms at 100 Hz).

![subwoofer phase not time](/assets/img/subwoofer_align_phase_not_time.png "Phase aligned but not time aligned")

As with the [magnitude method](#time-align-using-magnitude), the group delay plot can be consulted to double check the alignment.  This requires taking a new measurement with both speakers active.

In the example plots above, the crossovers were disabled to ensure the measurements had enough signal on either side of the crossover to see the phase slope.  Use caution when measuring with crossovers disabled as this could lead to audio system damage.  An alternative approach is to disable [Coherence Blanking](../manual/plot_setup.md#coherence-blanking).

The degree of success one will have with this method depends a lot on the audio system and the room.  Sometimes it is better to start with the magnitude method and fine tune using the phase method.


