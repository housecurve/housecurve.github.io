## How to tune an audio system

### Tuning an audio system
The process for tuning an audio system will generally involve the tasks described below:

[Select reference curve](#select-reference-curve).  The reference curve defines how the audio system will sound.  The choice of curve is subject to personal taste.

[Apply equalization](#apply-equalization).  Equalization means adjusting the volume level at different frequencies to match the reference curve.

For audio systems with separately adjustable speakers, such as a 2.1 system (main speakers and a subwoofer), the following steps should be performed before equalization:

[Match speaker levels](#match-speaker-levels).  The speakers of the audio system should be playing at roughly the same volume level in the listening area.  This is done to ensure measurements will reflect the whole audio system and also to avoid using equalization to correct level differences.

[Choose crossover frequencies](#choose-crossover-frequencies).  Crossover frequencies are used to define regions of responsibility for speakers.  This is important when using speakers that have a limited frequency range, such as a subwoofer.

[Time align speakers](#time-align-speakers)  When two speakers produce the same sound, time alignment ensures the sound arrives at the listening area at the same time.  When speakers are not time aligned, they will interfere with each other in ways that cannot be corrected by equalization.

It may be necessary to iterate over these tasks a few times to get things right.  Experimentation is encouraged to find what works for a given audio system.


### Select reference curve
A Reference Curve, or “house curve” is a target power measurement (aka “frequency response”) for an audio system in a room.

The idea is to adjust the audio system such that the power measurement matches the Reference Curve.  HouseCurve will display the selected Reference Curve on the power plot when there are measurements.

![](/assets/img/NoEqualizer.png)

The choice of Reference Curve is subject to individual taste.  Generally speaking, most listeners prefer a curve with a 1 dB/octave downward slope (-3 dB/decade).  Put simply, listeners prefer it when low frequencies are louder than high frequencies.  HouseCurve provides some common reference curves, all of which have the same overall downward slope.

In the audiophile world, a “flat” response is often seen as the ultimate goal.  However, for everyday listening, a flat response tends to sound overly “bright” and unpleasant.  HouseCurve can [import custom curves](/MANUAL.md#reference-curve), so by all means, try it for yourself: Flat Reference Curve.

The curves that ship with HouseCurve are intended for home audio.  In an automobile, it is very common for the Reference Curve to have a more pronounced low frequency hump.  This is done to overcome motor and road noise.  Due to the custom nature of these curves, a “car” curve is not provided.  However, a custom curve can be easily created using a simple text editor and then loaded into HouseCurve.  See [curve file format](/HOWTO.md#curve-file-format) for more information.

Below are some resources for understanding what reference curves do and how to choose them:
* [Advice on better house curve?](https://www.minidsp.com/forum/dirac-series-support/17523-advice-on-better-house-curve)
* [House Curve: What it is, why you need it, how to do it](https://www.hometheatershack.com/forums/rew-forum/96-house-curve-what-why-you-need-how-do.html)
* [Relevant loudspeaker tests, in studios, in Hi-Fi dealers' demo rooms, in the home etc](https://www.bksv.com/media/doc/17-197.pdf)
* [The Measurement and Calibration of Sound Reproducing Systems](http://www.aes.org/e-lib/browse.cfm?elib=17839)


### Apply equalization

If the audio system has separately adjustable speakers, such as a subwoofer, ensure that levels have been [matched](#match-speaker-levels), crossovers are [selected](#choose-crossover-frequencies) and speakers are [time aligned](#time-align-speakers).

Equalization in general means changing the volume level at different frequencies.  There are many ways an audio system can be changed to make this happen.  What can be changed depends on the audio system:

* Change speaker position in room
* Adjust the bass or treble controls
* Change relative levels of speakers (ex: subwoofer level)
* Adjust the graphic or parametric equalizer settings
* Change the room (ex: sound dampening, adjust furniture)

When equalizing, the goal is to adjust the audio system such that the average power measurement ends up within the +/- 3 dB band that surrounds the Reference Curve.

![](/assets/img/EqualizerStart.png)

Adjust the audio system in small steps, collecting the same measurements after each change.  [Overlays](/MANUAL.md#overlay) are helpful for seeing the effect of an adjustment as can be seen below:

![](/assets/img/EqualizerChanged.png)

When most of the average power measurement is within the reference band, the audio system is sufficiently equalized.  Further adjustments may not be perceptible.

Avoid adjustments that are beyond the capability of the audio system.  Doing so will lead to distortion and possibly audio system damage.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more signal power.  A change of +20 dB is 100 times more signal power!


### Match speaker levels
For systems with separately adjustable speakers, the relative levels need to be matched.  The goal is to set the speaker levels such that measurements in the listening area are roughly close to the reference curve on the power plot.

Make sure all speakers are active and set the overall audio system volume to a normal listening level.  It can be helpful to set HouseCurve’s [Display Mode](/MANUAL.md#display-mode) to History.

Take a measurement from the middle of the listening area.  On the power plot, observe how the measurement lines up with the Reference Curve.  Adjust individual speaker levels and repeat the measurement as needed to get close to the Reference Curve.

The example below shows an audio system consisting of main speakers and a subwoofer.  The subwoofer level was initially too low.  It was adjusted a few times to get close enough to the Reference Curve.

![](/assets/img/SubLevel.png)


### Choose crossover frequencies



### Time align speakers


