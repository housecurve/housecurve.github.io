---
layout: default

title: Time Alignment
parent: Tuning
nav_order: 4
---


# Time align speakers

When an audio system contains limited range speakers (subwoofers, bi-amped speakers, etc), time alignment becomes an important adjustment.  HouseCurve supports two methods:

- [**Magnitude method**](#time-align-using-magnitude).  This is the simpler of the two methods, but it can be less accurate.

- [**Phase method**](#time-align-using-phase).  This method is more accurate, but it requires more steps to measure correctly.


## What is time alignment?

At the crossover frequencies of an audio system, sound transitions from one speaker to another.  In this region, speakers on either side of the crossover are active.  If sound leaves the speakers at different times, [destructive interference](https://www.phys.uconn.edu/~gibson/Notes/Section5_2/Sec5_2.htm) (or “cancellation”) can occur leading to audible dips in the sound level at the crossover frequency.  These dips cannot be fixed by equalization.

The degree of time alignment needed is dependent on the wavelength of the crossover frequency (wavelength = 1 / frequency).  Destructive interference reaches a maximum when there is a half wavelength of delay between speakers.  For example, a subwoofer and a main speaker are separated by a crossover at 100 Hz.  The wavelength at 100 Hz is 0.01 seconds or 10 milliseconds (ms).  If the subwoofer is delayed by half a wavelength, or 5 ms, then peak destructive interference will occur.  The effect will subside for smaller or larger delays, ex: 0-2 ms or 8-10 ms.  

Since sound is a wave, the pattern of destructive interference will repeat at multiples of the crossover wavelength.  In the example above, peak destructive interference will happen for delays of 5 ms, 15 ms, 25 ms and so on.  This makes time alignment tricky as it’s possible to align on the wrong cycle and have more delay than needed.

The adjustments available for time alignment depend on the audio system:  

* Speaker location can be adjusted to add/remove delay (sound takes about 3 ms to travel 1 meter)
* Amplifiers/receivers typically have delay or distance settings.
* Active crossovers and parametric equalizers usually have delay settings too (a [MiniDSP 2x4 HD](https://www.minidsp.com/products/minidsp-in-a-box/minidsp-2x4-hd) was used for many of the measurements in this document).
* Subwoofers may have a control that permits adjusting phase from 0 to 180 degrees, this is the same as adjusting a delay or distance.
* You can switch the polarity of the speaker (subwoofers often have a switch labelled “phase” for this).

Most audio systems will have a combination of these adjustments, so experimentation will be required to figure out what works best.


## Time align using magnitude

Destructive interference will cause a dip in the magnitude measurement at the crossover frequency.  We can use this effect to figure out what adjustments increase or decrease the dip (polarity, phase, delay, distance, whatever you have).  The smaller the dip, the better the time alignment.

When using this method, it is important to avoid changing audio system levels (volume, bass/treble, equalizer, etc).

Set HouseCurve’s Plot Mode to [History](../manual/plot_setup.md#plot-mode).  Zoom into the region around the crossover frequency.

Set the [Target Curve Fit](../manual/plot_setup.md#target-curve-fit) to manual and select an appropriate level.  This will stop the target curve from shifting slightly between measurements, providing a better reference.

Ensure speakers on either side of the crossover are enabled.  Take a measurement from the middle of the listening area.  On the magnitude plot, place the cursor at the crossover frequency and observe the magnitude value.  Adjust the audio system.  Repeat the measurement and observe the new magnitude value.  Continue to make adjustments until the maximum magnitude level is achieved and the dip is the smallest.  The plot below shows a system being adjusted from the worst alignment (largest dip) to the best (smallest dip).

![subwoofer align magnitude](/assets/img/subwoofer_align_magnitude.png "Adjust until the smallest dip is found")

The downfall of this approach is that maximum magnitude can be achieved at multiples of the crossover wavelength.  This can lead to tuning the system with more delay than necessary.  The group delay plot can be used to check for this.  Excess delay will appear as a step change in group delay before or after the crossover.  The group delay plot below shows a system with increasing amounts of subwoofer delay.  The system is initally aligned at 100 Hz (darkest green).  As unnecessary wavelengths of delay are added, the group delay increases (at 100 Hz, one wavelength is 10 ms).

![subwoofer align groupdelay](/assets/img/subwoofer_align_group_delay.png "Check subwoofer alignment with group delay")

## Time align using phase

When two speakers are time aligned, their [phase plots](../usage/plot_types.md#phase-plot) will show the same value at the crossover frequency and the phase slopes will be roughly simlilar in the crossover region.

Time alignment using phase requires separate measurement of the speakers on either side of the crossover.  To do this with HouseCurve, measurements of the first speaker are [saved](../manual/plot_setup.md#saved-measurement) so that they can be compared to measurements of the second speaker.  As adjustments are made, measurements of the second speaker are repeated.

Phase measurements are very sensitive to changes in the distance between speaker and microphone.  For best results, take measurements from the middle of the listening area, keeping the microphone in the same location for each measurement.

In addition, phase measurements must share the same time reference to be compared.  To achieve this with HouseCurve, the chirp sound must come from one speaker for all measurements (see [measurement process](../usage/measurement_process.md)).  It is also necessary to disable the [Remove Delay](../manual/measure_setup.md#remove-delay) feature.

### Example

To demonstrate the phase method, we'll align a subwoofer with the main speakers of a typical 2.1 audio system.

The first step is to choose a "chirp" speaker for the timing reference.  Go to [measure setup](../manual/measure_setup.md#channels) and set the ***Chirp Channel*** to either left or right.  This will cause the chirp sound to come from only one of the main speakers.  Set the ***Sweep Channel*** to all.  This will cause the sweep sound to come from both main speakers, providing an average phase measurement at the chosen microphone location.

Disable the subwoofer and perform a measurement of the main speakers.  Save the measurement when you are satisfied.

Next, to measure the subwoofer we'll use a technique described here [subwoofer measurement](../usage/subwoofer.md).  Change the ***Sweep Channel*** to the opposite of the chirp.  This will prevent the chirp speaker from playing the sweep sound.  Disable the non-chirp main speaker and enable the subwoofer.  This will cause the sweep to play only from the subwoofer.

Set HouseCurve’s Plot Mode to [History](../manual/plot_setup.md#plot-mode).  Switch to the phase plot and zoom into the region around the crossover frequency.  Place the cursor at the crossover frequency.

Measure the subwoofer.  Measurements will appear on top of the saved main speaker measurement.  Make small adjustments to the audio system and repeat the subwoofer measurement until good alignment is found.  With the plot in history mode, you'll be able to see how the phase gradually changes.

The phase plot below shows a 2.1 audio system with good time alignment.  The subwoofer measurement (green) is compared to a saved measurement of the main speakers (grey).  The main speakers and subwoofer have nearly the same phase at the crossover frequency (100 Hz) and the phase slopes are roughly the same.

![subwoofer align phase](/assets/img/subwoofer_align_phase.png "Phase plot showing subwoofer aligned with main speakers")

The plot below shows the same audio system in various states of alignment.  As delay is changed, the phase of the subwoofer moves up or down at the crossover frequency.  The overall slope of the phase will also change.

![subwoofer phase change](/assets/img/subwoofer_align_phase_change.png "Phase plot showing different delay adjustments")

Counterintuitively, the subwoofer phase measurements above (green) were generated by delaying the main speakers (grey).  This works because delaying the main speakers also delays the chirp, which is the timing reference.  Subwoofers tend to have more delay to begin with, so delaying the main speakers to match is often the correct adjustment.

Finally, in the plot below, the audio system is aligned, but on the wrong cycle (too much delay).  While the main speakers and subwoofer have the nearly same phase at the crossover frequency, the phase slopes are different.  This is sometimes described as “phase aligned but not time aligned”.  In this situation, try adding or subtracting a delay of one crossover wavelength (ex: 10 ms at 100 Hz).  You can also try inverting the polarity (subwoofers sometimes have a switch labelled "phase" for this purpose).  This effectively adds or subtracts a delay of 1/2 a wavelength.  To remain phase aligned, it will also be necessary to add or subtract a delay of 1/2 a crossover wavelength (ex: 5 ms at 100 Hz).  It will take some experimentation to figure out what combination of polarity and delay works.

![subwoofer phase not time](/assets/img/subwoofer_align_phase_not_time.png "Phase aligned but not time aligned")

The degree of success one will have with the phase method depends a lot on the audio system and the room.  It is recommended that you try the [magnitude method](#time-align-using-magnitude) first, then fine tune with the phase method.

