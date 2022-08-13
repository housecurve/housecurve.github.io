---
layout: default

title: Target Curves
parent: Tuning
nav_order: 3
---


# Choose Target curve

A Target Curve, or “house curve”, is a visual guide to ensure you tune your audio system in the right direction.  The system is "tuned" when the average  measurement matches the Target Curve.

HouseCurve provides some common curves to experiment with.  These can be selected by going to [Plot Setup](../manual/plot_setup.md).  The "House" curves are flatter and intended for home listening.  The "Car" curves have significantly more bass which is common for automobile listing.  HouseCurve will display the selected curve on the magnitude plot when there are measurements.

![target curve](/assets/img/target_curve.png "Measurement compared to B&K target curve (yellow)")

The choice of Target Curve is subject to individual taste.  Typically, listeners prefer it when low frequencies are louder than high frequencies.  A  downward slope of 1 dB/octave is quite common.  Let your ears be the judge.

Custom curves can be created with a text editor and [imported](../manual/plot_setup.md#target-curve) into HouseCurve.  See [curve file format](../manual/file_formats.md#curve-file-format) for more information.  The curves provided by HouseCurve are a great starting point for making your own:

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


