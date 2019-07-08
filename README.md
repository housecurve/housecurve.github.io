## What Does HouseCurve Do?

Tune your audio system with your iPhone / iPad.

The space in which an audio system is used has a significant impact on the sound heard by the listener.  Tuning is required to compensate for the effects of the space such as changing equalizer settings, moving speakers, or installing room treatments.

The traditional way to tune an audio system is to play well known material and adjust the system until it “sounds good”.  This is hard to do in practice.  A common pitfall is the tendency to remaster the material rather than tune the system.  The result is a system that only sounds good when playing the material used for tuning.

HouseCurve avoids this pitfall by making it easy to tune an audio system to a reference curve.  This tuning technique is sometimes referred to as a “house curve”.  A house curve, broadly speaking, is an in-room frequency response that is regarded as “good sounding”.  Although the selection of curve is still a matter of taste, the process of tuning is straightforward - adjust the system’s in-room frequency response until it matches the reference curve.  The result is a system that performs well no matter what material is being played.

HouseCurve works by playing pink noise through the audio system and measuring the in-room frequency response.  Measurements are displayed on top of the reference curve, making it easy to determine how to adjust the system.

HouseCurve was designed to produce acceptable results with the iPhone / iPad microphone.  For users wanting higher accuracy, HouseCurve also supports calibrated external microphones.

### Features:

* Connects to audio system using AirPlay, Bluetooth or line-out
* In-room frequency response measurements using pink noise
* Rapid collection and averaging of measurements
* Automatically discards bad measurements
* Automatically scales and centers plot
* Includes common reference curves
* Supports custom reference curves
* Provides compensation for iPhone/iPad microphones
* Supports external microphones and calibration files
* Adjustable fractional octave smoothing
* Decade or octave frequency scales

For custom reference curves and microphone calibration, HouseCurve supports the following (de facto) standard:  A space or tab delimited text file with a frequency (Hz) followed by a gain (dB) on each line.  A third phase value may be included but is ignored.  Lines starting with non-numeric characters are ignored.  Frequencies must be listed in increasing order.  HouseCurve will interpolate a curve from 20-20000 Hz using the values provided.  The file extension may be _txt_ or _frd_.

[Example Reference Curve](/examples/curve.txt)

## How To Use

[How To Use](/HELP.md)

## FAQ

[FAQ](/FAQ.md)

## Privacy Policy

HouseCurve does not collect, use, store or transfer personal data.  With your permission, Apple collects app analytics to help developers improve their apps.  For more information, see [Apple Privacy Policy](https://www.apple.com/privacy/).

## EULA

[Apple Standard License Agreement](https://www.apple.com/legal/internet-services/itunes/dev/stdeula)



