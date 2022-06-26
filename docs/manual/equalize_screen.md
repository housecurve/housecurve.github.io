---
layout: default

title: Equalize Screen
parent: Manual
nav_order: 5
---

## Equalize Screen
The Equalize Screen is the main interface for the automatic equalization / room correction tool.  It displays the filters used to correct a saved measurement to the target curve. The lower toolbar contains controls related to equalization.

![Equalize Screen](/assets/img/equalize_screen.png "HouseCurve Equalize screen")

- **Predicted output** The predicted magnitude measurement is shown in cyan.  After applying the correction filters, the measured magnitude response should be close to this.

- **Correction filters** The filters needed to correct the saved measurement (grey) to the target curve (yellow) are shown in magenta.

- **Filter Detail** Tap to show the individual filter parameters.  HouseCurve's biquad filters are based on the [Audio EQ Cookbook by Robert Bristow-Johnson](https://www.w3.org/TR/audio-eq-cookbook/).  Where Frequency is the center frequency of the filter.  Gain is in dBFS and Q is the width of the filter (for peaking biquad Q is a "proportional Q").

- **Plot Setup** Tap to show the [Plot Setup Screen](#plot-setup-screen).  This is shared with the [Measure Screen](#measure-screen).

- **Equalize Setup** Tap to show the [Equalize Setup Screen](#equalize-setup-screen).

- **Filter Export** Tap to show the [Filter Export Screen](#filter-export-screen).



