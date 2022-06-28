---
layout: default

title: Filter Export
parent: Manual
nav_order: 7
---

## Filter Export

<img src="/assets/img/filter_export.png" alt="Filter export screen" class="app-portrait">

### Format
This is the format of the export file.  The following formats are supported:

- **Biquad Coefficients** Export biquad transfer function coefficients b0, b1, b2, a1, a2 where a0 is normalized to 1.0, and the signs of a1, a2 are flipped.  This format is common, ex: it is compatible with [miniDSP](https://www.minidsp.com) hardware, but it may not be compatible with all equalizers.  As a precaution, turn the volume down on the first import of this file.  If you experience problems, please [reach out](mailto:support@housecurve.com).

- **Parametric EQ Settings** Export parametric equalizer settings (frequency, gain, Q) using this [format](https://sourceforge.net/p/equalizerapo/wiki/Configuration%20reference)

### Sample Rate
This is the sample rate of the equalizer (not the audio source).

### Export
Press to initiate the file export.


