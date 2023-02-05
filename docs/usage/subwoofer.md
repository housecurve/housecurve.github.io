---
layout: default

title: Subwoofer Measurements
parent: Usage
nav_order: 7
---


# Subwoofer measurements
A subwoofer (or woofer) lacks the frequency range to play the chirp sound of the test signal (see [measurement process](measurement_process.md)).  To measure a subwoofer with HouseCurve, another full range speaker is needed to produce the chirp and serve as the timing reference.

HouseCurve can be configured to play the chirp and sweep sounds on [different audio channels](../manual/measure_setup.md#chirp-and-sweep-channel).  This makes it possible to route the sweep to the subwoofer and the chirp to another speaker (typically a main or center speaker).  Not all audio systems will support this.

For a typical 2.1 audio system, this can be accomplished by disabling (or disconnecting) a main speaker, ex: the right speaker.  HouseCurve is then configured to play the sweep through the right channel and the chirp through the left channel.  The subwoofer will receive the right channel via the “subwoofer out” of the audio system.  This is pictured below:

![subwoofer measurement connections](/assets/img/subwoofer_measurement_sweep.png "Signal paths for subwoofer measurement")

Use [Coherence Blanking](../manual/plot_setup.md#coherence-blanking) to ensure the plots only show portions of the measurement that are actually from the subwoofer and not simply noise.  The plot below shows a subwoofer measurement with Coherence Blanking turned off.  As can be seen, the plot shows a peak where the subwoofer is actually able to produce sound.  The rest of the measurement is the noise floor of the audio system and room.

![subwoofer no blanking](/assets/img/subwoofer_no_coherence_blanking.png "Subwoofer measurement without coherence blanking")

Below the same measurement is shown with Coherence Blanking set to 50%.  Now only the useful portion of the measurement is shown.

![subwoofer coherence blanking](/assets/img/subwoofer_coherence_blanking.png "Subwoofer measurement with coherence blanking")

When separately adjusting main and subwoofer speakers to the same target curve, it is recommended that the [Target Curve Fit](../manual/plot_setup.md#target-curve-fit) setting be switched to manual and a suitable level entered.  The target curve will then appear at the same level for all measurements.  In the examples above, the target curve was fixed at 24.5 dB @ 100 Hz.



