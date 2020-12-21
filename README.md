## What Does HouseCurve Do?

HouseCurve is a tool for visually comparing the sound of your audio system to a reference curve.

![](/assets/img/iPhoneScreen.png)

### Features:

* Rapid collection of sine sweep or pink noise measurements
* Average and historical measurement display modes
* Automatic measurement validation (sound level and interference)
* Three common reference curves are included
* Supports custom reference curves
* Adjustable fractional octave smoothing
* Decade or octave frequency scales
* Works with AirPlay, Bluetooth or line-out
* Supports external microphones

### How does it work?
HouseCurve was designed for tuning audio systems.  For example, manually adjusting an equalizer in a home or car stereo.

HouseCurve works by playing a log sine sweep through your audio system and measuring the in-room frequency response.  Multiple measurements may be averaged to fully capture how the system sounds in the listening area.  Measurements are displayed on top of the reference curve, making it easy to determine how to adjust your system.  By making small adjustments and repeating measurements, you can tune your system to the reference curve.

HouseCurve was designed to produce acceptable results with the iPhone / iPad microphone.   For users wanting higher accuracy, HouseCurve also supports calibrated external microphones.

For custom reference curves and microphone calibration, HouseCurve supports the following (de facto) standard:  A space or tab delimited text file with a frequency (Hz) followed by a gain (dB) on each line.  A third phase value may be included but is ignored.  Lines starting with non-numeric characters are ignored.  Frequencies must be listed in increasing order.  HouseCurve will interpolate a curve from 20-20000 Hz using the values provided.  The file extension may be _txt_ or _frd_.

[Example Reference Curve](/examples/curve.txt)

## Privacy Policy

HouseCurve does not collect, use, store or transfer personal data.  With your permission, Apple collects app analytics to help developers improve their apps.  For more information, see [Apple Privacy Policy](https://www.apple.com/privacy/).

## EULA

[Apple Standard License Agreement](https://www.apple.com/legal/internet-services/itunes/dev/stdeula)



