---
layout: default

title: Equalization
parent: Tuning
nav_order: 5
---


# Apply equalization
If the audio system has separately adjustable speakers, such as a subwoofer, ensure that levels have been [matched](match_levels.md), crossovers are [selected](crossover.md) and speakers are [time aligned](time_align.md).

HouseCurve supports automatic and manual equalization:

- [**Automatic equalization**](#automatic-equalization) - HouseCurve generates a set of biquad filters to correct a saved measurement to a target curve.  The filter parameters can then be exported to a [file](../manual/file_formats.md#filters) and loaded into your audio system (ex: parametric equalizer, convolution engine, etc).  Even if you can't import the filters - you can see what HouseCurve would adjust and use that as a guide.

- [**Manual equalization**](#manual-equalization) - HouseCurve is used to guide manual tuning.  This is the most straight forward approach.  It works by iteratively measuring the audio system, adjusting it, then measuring again.  It will work with any audio system, even ones with limited adjustments (ex: you can move furniture and see the impact).


## What is equalization / room correction?

Equalization means adjusting an audio system’s output so that the response measured in the listening area aligns with a target curve.  It is used to correct for characteristics of the audio system, or for the effects of the room (aka “room correction”).  Since it is normally difficult to separate audio system from room, we are usually correcting for both at the same time.

When sound leaves an audio system, it interacts with the room, but this interaction changes with frequency.  Below the Schroeder frequency, or about 300 Hz, room resonances have a dominant impact on what is heard in the listening area.  At these frequencies, the room is in control.  Above the Schroeder frequency, direct sound from the audio system begins to dominate with contributions from room diffusion, absorption and reflection.  In this region, the audio system is mostly in control.  Thus, when equalizing a typical home or car audio system, we are correcting for the room below the Schroeder frequency and for the audio system above it (for an excellent deep dive, please read [Floyd Toole’s paper](https://www.harman.com/documents/AudioScience_0.pdf)).

When applying equalization, it is best to start at the low frequencies and work your way up.  At low frequencies, room resonances will create large peaks and dips in the magnitude.  These will be quite audible, so focus on smoothing them out to the target curve.  Moving toward higher frequencies, peaks and dips become much less audible and should not be adjusted.  Instead, shift your focus to adjusting wide regions of the magnitude response towards the target curve (an octave or more).  At the very upper end (10 KHz), it may not be worth making any adjustments at all (A great video on the topic is [here](https://www.youtube.com/watch?v=TwGd0aMn1wE)).


## Gain management

Equalization adjusts the audio system gain at different frequencies through "boosts" and "cuts".  In order to avoid pushing your audio system too hard and causing distortion, please follow these recommendations:

1. **Equalize the average of several measurements in the listening area** - A single measurement will have narrow deep dips caused by standing waves known as [room modes](https://en.wikipedia.org/wiki/Room_modes).  The dip is measured when the microphone is in a location where a standing wave has an antinode.  Boosting the dip has no effect at this location, but it will elsewhere in the room, leading to boomy sound and possibly distortion.  Since the dips are location dependent, averaging helps to hide them, providing a better overall measurement of the listening area.

1. **Lower the target curve** - To avoid increasing the overall gain, you can manually lower the target curve (see: [target curve fit](../manual/plot_setup.md#target-curve-fit)).  This will cause more of the measurement to appear above the target curve, effectively increasing the number and size of cuts needed to correct.  The results is lower overall system gain.

1. **Avoid correcting beyond the capabilites of the system** - A small bookshelf speaker may have a low frequency limit of 50 Hz (-6 dB).  Applying a +10 dB boost at 30 Hz to get more bass is going to drive the speaker beyond its capabilities and lead to distortion (and possibly damage).  When [Coherence Blanking](../manual/plot_setup.md#coherence-blanking) is enabled, the low frequency capability of the speaker is more obvious.  If the speaker can't produce 30 Hz, this portion of the measurement will not be displayed.


## Automatic Equalization

HouseCurve's [Equalize Tool](../manual/equalize_tool.md) generates filters to correct a [saved measurement](../manual/plot_setup.md#saved-measurement) to a [target curve](../manual/plot_setup.md#target-curve).  It can be accessed from the more menu <img src="/assets/img/more.png" alt="More" class="app-icon">.

For best results, average several measurements from the listening area and then save.  Averaging provides HouseCurve with a better picture of how sound changes in the listening area.

The image below shows a saved measurement (grey) being corrected to the target curve (yellow).  The filters that perform the correction are shown in magenta.  The predicted magnitude response (when filters are applied) is shown in cyan.

![equalize tool](/assets/img/equalize_biquads.png "Equalize tool showing correction filters and predicted output")

HouseCurve allocates filters to regions with the largest deviation from the target curve, starting with lower frequencies and ignoring blanked regions (see [Coherence Blanking](/../manual/plot_setup.md#coherence-blanking)).  The algorithm’s behavior can be controlled by tapping <img src="/assets/img/setup.png" alt="Setup" class="app-icon"> to display the [equalize setup screen](../manual/equalize_setup.md).  Plot settings, such target curve fit and blanking threshold also impact the algorithm.  The display automatically updates to reflect any setting change.

HouseCurve uses a form of IIR filter known as a peaking biquad filter.  These are commonly used in graphic and parametric equalizers to boost or cut at various frequencies.  You can view the individual filters by tapping <img src="/assets/img/detail.png" alt="Detail" class="app-icon"> to bring up the Filter Detail screen, shown below.  This screen can be used to manually enter filter settings into your audio system.

![filter detail screen](/assets/img/equalize_detail.png "Filter details can be imported into your audio system")
{: .app-portrait }

The filters can be [exported](../manual/filter_export.md) to a file by tapping <img src="/assets/img/export.png" alt="Export" class="app-icon">.  For more information see [file formats](../manual/file_formats.md#filters).

When the filters have been loaded into your audio system, you should find that measurements are reasonably close to the predicted response.  The screenshots below show the predicted response (cyan) and actual measurements (green) after applying the filters.

![equalize tool](/assets/img/equalize_biquads_before.png "Equalize tool's predicted output")

![measurement after equalizing](/assets/img/equalize_measure_after.png "Measured results will be reasonably close to predicted")

If your results are radically different from the prediction, check that the filter sample rate is correct - a mismatch will cause the filters to be applied to the wrong frequency.  The file format may also be incompatible with your audio system.  If you have questions or experience problems, please [reach out](mailto:support@housecurve.com).

The following application notes dive into the details of creating filters:

* [Roon](../appnotes/roon.md) - impulse response
* [miniDSP 2x4HD](../appnotes/minidsp.md) - biquad coefficients
* [Volumio3 with FusionDSP](../appnotes/volumio.md) - parametric EQ settings

In addition, HouseCurve's filters have been tested on these systems:

* [moOde Audio](https://moodeaudio.org) - impulse response
* [Equalizer APO](https://sourceforge.net/projects/equalizerapo/) - parametric EQ settings
* [HifiBerry DAC+DSP](https://www.hifiberry.com/shop/boards/hifiberry-dac-dsp/) - parametric EQ settings


## Manual Equalization

Equalization means changing the volume level at different frequencies.  There are many ways an audio system can be changed to make this happen:

* Change speaker position in room
* Adjust the bass or treble controls
* Change relative levels of speakers (ex: subwoofer level)
* Adjust the graphic or parametric equalizer settings
* Change the room (ex: sound dampening, adjust furniture)

When equalizing, the goal is to adjust the audio system such that the average magnitude measurement ends up within the +/- 3 dB band that surrounds the target curve.

![equalization start](/assets/img/equalizer_start.png "Adjust until measurement within target curve band")

Adjust the audio system in small steps, collecting the same measurements after each change.  [Saved measurements](../manual/plot_setup.md#saved-measurement) are helpful for seeing the effect of an adjustment as can be seen below.  You can also take a look at the [Equalize Tool](#automatic-equalization) to see what HouseCurve would equalize (based on the saved measurement).

![equalization changed](/assets/img/equalizer_changed.png "Save measurements to see what adjustment did")

When most of the average magnitude measurement is within the target band, the audio system is sufficiently equalized.  Further adjustments may not be perceptible.




