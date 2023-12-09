---
layout: default

title: Equalize Tool
parent: Manual
nav_order: 3
---

# Equalize Tool
The Equalize Tool can be accessed from the more menu <img src="/assets/img/more.png" alt="More" class="app-icon"> on the Measure screen.  It is the main interface for automatic equalization / room correction.  The plot area displays the filters used to correct a saved measurement to a target curve. The lower toolbar contains controls related to equalization.

![Equalize tool](/assets/img/equalize_screen.png "HouseCurve Equalize tool")

## Predicted output
The predicted magnitude measurement is shown in cyan.  After applying the correction filters, the measured magnitude response should be close to this.

## Correction filters
The filters needed to correct the saved measurement (grey) to the target curve (yellow) are shown in magenta.

## Filter Detail
Tap <img src="/assets/img/detail.png" alt="Detail" class="app-icon"> to show the individual filter parameters.  HouseCurve's biquad filters are based on the [Audio EQ Cookbook by Robert Bristow-Johnson](https://www.w3.org/TR/audio-eq-cookbook/).  Where Frequency is the center frequency of the filter.  Gain is in dB and Q is the width of the filter (constant Q).

## Plot Setup
Tap <img src="/assets/img/plot.png" alt="Plot Setup" class="app-icon"> to show the [Plot Setup screen](plot_setup.md).  Use this to select target curves and saved measurements.

## Equalize Setup
Tap <img src="/assets/img/equalize_setup.png" alt="Equalize Setup" class="app-icon"> to show the [Equalize Setup screen](equalize_setup.md).

## Filter Export
Tap <img src="/assets/img/export.png" alt="Export" class="app-icon"> to show the [Filter Export screen](filter_export.md).



