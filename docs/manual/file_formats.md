---
layout: default

title: File Formats
parent: Manual
nav_order: 9
---

# File Formats

HouseCurve can read/write any files that are visible from the [Files](https://apps.apple.com/ca/app/files/id1232058109) app.  This includes local storage on the iPhone/iPad, but also iCloud, Samba, DropBox, OneDrive, etc.

To use a file from a website, download it to the local iPhone/iPad storage and then select from within HouseCurve.

To transfer files, you can just use HouseCurve to save to the desired location.  Or you can save to the local storage and then share with text message, email, AirDrop, etc.


## Curves

A space or tab delimited text file with a frequency (Hz) followed by a gain (dB) on each line. A third phase value may be included but is ignored. Lines starting with non-numeric characters are ignored. Frequencies must be listed in increasing order. HouseCurve will interpolate a curve from 20-20000 Hz using the values provided. The file extension may be txt or frd.

[Example target curve](/curves/curve.txt)


## Measurements

Saved measurements can be exported as impulse responses for use in other tools.  The file format is a monural [WAV](https://en.wikipedia.org/wiki/WAV). Samples are 32-bit floating point.  The impulse response is windowed to be 500 ms in length, with the peak occurring at the first sample.  The file is padded out to 1 second in length.


## Filters

HouseCurve supports the same filter formats as [REW](https://www.roomeqwizard.com/help/help_en-GB/html/equaliser.html).  These are quasi-standard, but may not work with all equalizers.  When trying this out for the first time, turn the volume down as a precaution.  For support, questions and suggestions, please [reach out](mailto:support@housecurve.com).


### Biquad Coefficients

A text file containing [biquad](https://en.wikipedia.org/wiki/Digital_biquad_filter) transfer function coefficients b0, b1, b2, a1, a2 where a0 is normalized to 1.0, and the signs of a1, a2 are flipped.  This format depends on the selected sample rate.  The file extension is txt.

[Example biquad coefficients](/filters/biquad.txt)

This format is compatible with [miniDSP](https://www.minidsp.com) hardware.  For other equalizers (ex: [CamillaDSP](https://github.com/HEnquist/camilladsp)), the signs of a1 and a2 need to be flipped.


### Parametric EQ Settings

A text file containing human-readable equalizer settings (frequency, gain, Q).  See [format](https://sourceforge.net/p/equalizerapo/wiki/Configuration%20reference#filter) for more information.  The file extension is txt.

[Example peq settings](/filters/peq.txt)

This format is meant for systems with a parametric equalizer, such as [Volumio](https://volumio.com/en/), [HifiBerry](https://www.hifiberry.com), [Equalizer APO](https://sourceforge.net/projects/equalizerapo/), etc.


### Impulse reponses

A monural [WAV](https://en.wikipedia.org/wiki/WAV) formatted audio file containing the impulse response of all filters together.  Samples are 32-bit floating point.  The impulse peak is at the first sample, normalized to 1.0.  The length of the impulse is 500 ms (number of samples will depend on the sample rate).

This format is meant for audio systems with a convolution engine (aka "convolver") such as [Roon](https://help.roonlabs.com/portal/en/kb/articles/dsp-engine-parametric-equalizer), [moOde](https://moodeaudio.org), [CamillaDSP](https://github.com/HEnquist/camilladsp), [Volumio](https://volumio.com/en/), etc.

It is normal for a change in overall system gain to happen when using a convolver.  You will need a way to adjust the overall gain to avoid distortion.


## Test signal

A stereo [WAV](https://en.wikipedia.org/wiki/WAV) formatted audio file containing the "chirp" and "sweep" sounds.  Samples are 32-bit floating point.  The sample rate is 44.1 KHz.  See [externally played sweeps](../usage/connecting.md#externally-played-sweeps) for more information.


