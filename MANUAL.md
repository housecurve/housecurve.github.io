## HouseCurve Manual
{:.no_toc}

1. table of contents inserted here
{:toc}

### Measure Screen
HouseCurve's main interface is the Measure Screen.  This is where measurements of an audio system are displayed.  Additional tools and the help screen can be accessed from the more menu <img src="/assets/img/more.png" alt="More" width="15">.  The lower toolbar contains controls related to measurement.

![measure screen](/assets/img/measure_screen.png "housecurve Measure screen")

- **Page Control** Tap to move between [magnitude, phase and group delay plots](/USAGE.md#plots) plots.  Alternatively, swipe from the left or right edge of the screen to change plots.

- **Airplay** Tap to select from available AirPlay and Bluetooth audio outputs.  The analog (wired) output is automatically selected when something is plugged into the iPhone/iPad headphone connector.  See [connecting to an audio system](/USAGE.md#connecting-to-an-audio-system).

- **More Menu** Tap to show additional tools and the help screen.

- **Measure** Tap to start [measurement process](/USAGE.md#measurement-process).  Tap again to to stop.  This button is disabled when not connected to an audio system.

- **Undo** Tap to discard the most recent measurement.  This button is disabled when there are no measurements.

- **Measure Setup** Tap to show the [Measure Setup Screen](#measure-setup-screen).

- **Plot Setup** Tap to show the [Plot Setup Screen](#plot-setup-screen).

- **Save Measurement** Tap to [save a measurement](#saved-measurement).  This button is disabled when there are no measurements on the plot.

- **Reset** Tap to discard all measurements.


### Plot Area
![housecurve plot area](/assets/img/plot_area.png "HouseCurve Measure plot area")

- **Target Curve** The [Target Curve](#target-curve) is displayed on the magnitude plot in yellow with +/- 3 dB bands. The phase and group delay plots always have a target of zero.

- **Saved Measurement** The [saved measurement](#saved-measurement) is displayed in grey.  The name of the measurement is displayed in Setup Status.

- **Measurements** Measurements are displayed on the plot in green.

- **Cursor** Tap plot area to show cursor, move with a single finger, tap again to hide.

- **Measurement Status** HouseCurve displays the status of the [measurement process](/USAGE.md#measurement-process) in this area.  The status disappears after a few seconds.

- **Setup Status** HouseCurve displays setup information in this area.  The status disappears after a few seconds.

- **Zoom / Scroll** To zoom into a plot, pinch anywhere on the plot area.  The plot can be scrolled left or right with two fingers.  Plot zoom and scroll only change the horizontal frequency axis.  HouseCurve automatically sets the vertical axis of the plots to show the measurement.


### Plot Setup Screen

#### Saved Measurement
Saved Measurements can be displayed on the plot for comparison.  Only one saved measurement can be selected at a time.  Select None to disable.  Measurements can be removed by tapping Edit.

Save a measurement by tapping [<img src="/assets/img/save.png" alt="Save" width="15">](#save-measurement) on the Measure screen.  The [Display Mode](#display-mode) controls what is saved.  In Average mode, the average measurement is saved.  In History mode, the most recent measurement is saved.  If a measurement with the same name exists, it can be overwritten.  

#### Target Curve
A [Target Curve](/TUNING.md#choose-target-curve) is displayed on the magnitude plot to serve as a guide for [tuning an audio system](/TUNING.md).  

The curve is positioned on the magnitude plot based on the Target Curve Fit setting.

Additional target curves can be loaded by tapping + at the top of the Target Curve screen.  Target curves can be removed by tapping Edit.

HouseCurve supports the following [Curve file format](/USAGE.md#curve-file-format).

#### Target Curve Fit
By default, the selected Target Curve is automatically fitted to measurements based on the [Display Mode](#display-mode).  In Average mode, the average measurement is used.  In History mode, the most recent measurement is used.

[Coherence Blanking](#coherence-blanking) also affects how the Target Curve is positioned.  Portions of the measurement below the blanking threshold are ignored for fitting.

When automatic fitting is disabled, the curve can be manually positioned by setting a desired dB level at 100 Hz.  This is useful when separately adjusting speakers to a common level, such as main speakers and a subwoofer.

#### Display Mode
HouseCurve can display measurements to suit a given task.

- **Average** mode (default) is used to capture how an audio system sounds in a listening area. Use this mode when tuning the audio system to match a target curve.  Measurements are included in an average as they are collected.  The average measurement is displayed in bold green. Individual measurements will appear in faded green.

- **History** mode is used to see the effect of an adjustment from a single microphone location. Use this mode for initial audio system setup, such as speaker position or time alignment.  The most recent measurement is displayed in bold green.  Older measurements appear in green and are faded according to age.

#### Smoothing
Smoothing can be applied to measurements to make it easier to see trends.  To remove smoothing, select None.

#### Coherence Blanking
Coherence blanking hides portions of the measurement that are [low quality](/USAGE.md#measurement-quality) and should not be used for tuning.  

Blanking occurs wherever the measurement falls below the selected signal to noise ratio (blanking threshold).  To disable blanking, select Off.

This setting also controls the threshold at which HouseCurve will [automatically discard measurements](/USAGE.md#low-measurement-coherence).

#### Frequency Scale
The frequency axis can have an Octave or Decade scale.  This setting applies to all plots.


### Measure Setup Screen

#### Chirp and Sweep Channel
The "chirp" and "sweep" sounds of the test signal can be played on different channels (see [measurement process](/USAGE.md#measurement-process)).  This is mainly used for [subwoofer measurements](/USAGE.md#subwoofer-measurements).

#### Stimulus Type
Stimulus Type controls the test signal used to measure the audio system.

In most cases, the **Sine Sweep** should be used as it will produce measurements with a higher signal to noise ratio.  In this mode, HouseCurve requires a connection to the audio system in order to play the test signal.

**External Sine Sweep** mode does not require a connection to the audio system.  Instead, the test signal must be manually transferred to the audio system (ex: using an SD card).  During the measurement process, the audio system is responsible for playing the test signal and HouseCurve listens for it.

The test signal can be exported to a WAV file when this mode is selected.  Note - chirp and sweep channel setting will be used to produce the test signal file.

**Pink Noise** is provided for interest sake.  Measurements based on pink noise will have a lower signal to noise ratio.

HouseCurve uses coherent averaging.  This has an interesting effect on Pink Noise measurements.  In a sonically treated room, such as one with sound absorbing panels on the walls, Pink Noise noise measurements will closely match Sine Sweep measurements.  In a more typical “reflective” room, Pink Noise magnitude measurements tend to be lower above ~2 KHz.  The degree to which the Pink Noise and Sine Sweep measurements match is an indication of how “dead” the room is.

#### Internal Mic Compensation
The built in iPhone/iPad microphones have a reasonably flat response and are quite acceptable for tuning an audio system.  However, when compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum.  

Internal Mic Compensation applies a moderate boost below 60 Hz and above 16 KHz to measurements made with the built in iPhone/iPad microphone.

#### External Mic Calibration
HouseCurve supports calibrated external microphones.  Available calibrations will be displayed in the list.  Select None to disable calibration.

Microphone calibrations can be loaded tapping + at the top of the External Mic Calibration screen.  Calibrations can be removed by tapping Edit.

HouseCurve supports the following [Curve file format](/USAGE.md#curve-file-format).


### Equalize Screen
The Equalize Screen is the main interface for the automatic equalization / room correction tool.  It displays the filters used to correct a saved measurement to the target curve. The lower toolbar contains controls related to equalization.

![Equalize Screen](/assets/img/equalize_screen.png "HouseCurve Equalize screen")

- **Predicted output** The predicted magnitude measurement is shown in cyan.  After applying the correction filters, the measured magnitude response should be close to this.

- **Correction filters** The filters needed to correct the saved measurement (grey) to the target curve (yellow) are shown in magenta.

- **Filter Detail** Tap to show the individual filter parameters.  HouseCurve's biquad filters are based on the [Audio EQ Cookbook by Robert Bristow-Johnson](https://www.w3.org/TR/audio-eq-cookbook/).  Where Frequency is the center frequency of the filter.  Gain is in dBFS and Q is the width of the filter (for peaking biquad Q is a "proportional Q").

- **Plot Setup** Tap to show the [Plot Setup Screen](#plot-setup-screen).  This is shared with the [Measure Screen](#measure-screen).

- **Equalize Setup** Tap to show the [Equalize Setup Screen](#equalize-setup-screen).

- **Filter Export** Tap to show the [Filter Export Screen](#filter-export-screen).


### Equalize Setup Screen

#### Maximum filters
The number of filters to use for correction.

Set this to the number of filters your parametric equalizer supports.  HouseCurve may not use all the filters.  HouseCurve currently only supports peaking filters (no shelving filters, etc.  If you would find this useful, please [reach out](mailto:support@housecurve.com)).

#### Frequency
The frequency range to equalize.  

Use the minimum frequency to prevent the algorithm from correcting low frequencies beyond the capabilities of the audio system, ex: trying to boost at 20 Hz when the audio system can barely produce 40 Hz at -6 dBFS.  Doing so will lead to distortion and possibly audio system damage.

The maximum frequency can be used to avoid wasting filters on high frequency issues that may not be audible.

#### Gain
The gain range for filters (absolute gain).

Use the minimum gain to prevent the creation of very small (and likely inaudible) filters.

The maximum gain limits the size of a boost or a cut an individual filter can make.  HouseCurve may place filters in close proximity to produce larger gains.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more signal power.

### Filter Export Screen

### Format
This is the format of the export file.  The following formats are supported:

- **Biquad Coefficients** Export biquad transfer function coefficients b0, b1, b2, a1, a2 where a0 is normalized to 1.0, and the signs of a1, a2 are flipped.  This format is common, ex: it is compatible with [miniDSP](https://www.minidsp.com) hardware, but it may not be compatible with all equalizers.  As a precaution, turn the volume down on the first import of this file.  If you experience problems, please [reach out](mailto:support@housecurve.com).

- **Parametric EQ Settings** Export parametric equalizer settings (frequency, gain, Q) using this [format](https://sourceforge.net/p/equalizerapo/wiki/Configuration%20reference)

#### Sample Rate
This is the sample rate of the equalizer (not the audio source).

#### Export
Press to initiate the file export.


