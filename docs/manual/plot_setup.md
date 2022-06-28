---
layout: default

title: Plot Setup
parent: Manual
nav_order: 2
---

## Plot Setup Screen

### Saved Measurement
Saved Measurements can be displayed on the plot for comparison.  Only one saved measurement can be selected at a time.  Select None to disable.  Measurements can be removed by tapping Edit.

Save a measurement by tapping [<img src="/assets/img/save.png" alt="Save" width="15">](#save-measurement) on the Measure screen.  The [Display Mode](#display-mode) controls what is saved.  In Average mode, the average measurement is saved.  In History mode, the most recent measurement is saved.  If a measurement with the same name exists, it can be overwritten.  

### Target Curve
A [Target Curve](/TUNING.md#choose-target-curve) is displayed on the magnitude plot to serve as a guide for [tuning an audio system](/TUNING.md).  

The curve is positioned on the magnitude plot based on the Target Curve Fit setting.

Additional target curves can be loaded by tapping + at the top of the Target Curve screen.  Target curves can be removed by tapping Edit.

HouseCurve supports the following [Curve file format](../usage/file_formats.md#curve-file-format).

### Target Curve Fit
By default, the selected Target Curve is automatically fitted to measurements based on the [Display Mode](#display-mode).  In Average mode, the average measurement is used.  In History mode, the most recent measurement is used.

[Coherence Blanking](#coherence-blanking) also affects how the Target Curve is positioned.  Portions of the measurement below the blanking threshold are ignored for fitting.

When automatic fitting is disabled, the curve can be manually positioned by setting a desired dB level at 100 Hz.  This is useful when separately adjusting speakers to a common level, such as main speakers and a subwoofer.

### Display Mode
HouseCurve can display measurements to suit a given task.

- **Average** mode (default) is used to capture how an audio system sounds in a listening area. Use this mode when tuning the audio system to match a target curve.  Measurements are included in an average as they are collected.  The average measurement is displayed in bold green. Individual measurements will appear in faded green.

- **History** mode is used to see the effect of an adjustment from a single microphone location. Use this mode for initial audio system setup, such as speaker position or time alignment.  The most recent measurement is displayed in bold green.  Older measurements appear in green and are faded according to age.

### Smoothing
Smoothing can be applied to measurements to make it easier to see trends.  To remove smoothing, select None.

### Coherence Blanking
Coherence blanking hides portions of the measurement that are [low quality](../usage/measurement_quality.md) and should not be used for tuning.  

Blanking occurs wherever the measurement falls below the selected signal to noise ratio (blanking threshold).  To disable blanking, select Off.

This setting also controls the threshold at which HouseCurve will [automatically discard measurements](../usage/measurement_process.md).

### Frequency Scale
The frequency axis can have an Octave or Decade scale.  This setting applies to all plots.



