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

### Match speaker levels

### Choose crossover frequencies

### Time align speakers


