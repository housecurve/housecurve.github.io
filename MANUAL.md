## HouseCurve Manual

### Main Screen
![](/assets/img/MainInterface.png)

#### Page Control
HouseCurve displays measurements on [power, phase and group delay plots](/HOWTO.md#plots).  Tap the page buttons to move between plots.  Alternatively, swipe from the left or right edge of the screen to change plots.

#### Help
Tap for Help screen

#### Setup
Tap for [Setup Screen](#setup) screen

#### Measure
Tap the Measure button to start [measurement process](/HOWTO.md#measurement-process).  Tap again to to stop.  This button is disabled when not connected to an audio system.

#### Undo
Tap the Undo button to discard the most recent measurement.  This button is disabled when there are no measurements.

#### Airplay
Tap the AirPlay button to select from available AirPlay and Bluetooth audio outputs.  The analog (wired) output is automatically selected when something is plugged into the iPhone/iPad headphone connector.  See [connecting to an audio system](/HOWTO.md#connecting-to-an-audio-system).

#### Reset
Tap to discard all measurements.

#### Save overlay
Tap to create an overlay from a measurement [Overlay](#Overlay).  This button is disabled when there are no measurements on the plot.


### Plot area
![](/assets/img/PlotArea.png)

#### Selected Reference Curve
The selected [reference curve](#reference-curve) is displayed on the power plot in yellow with +/- 3 dB bands.

The phase and group delay plots always have a reference of zero.

#### Selected Overlay
The selected [Overlay](#Overlay) is displayed in grey.  The name of the overlay is displayed in Setup Status.

#### Current Measurements
Measurements are displayed on the plot in green.

#### Cursor
Tap plot area to show cursor, move with a single finger, tap again to hide.

#### Measurement Status
HouseCurve displays the status of the [measurement process](/HOWTO.md#measurement-process) in this area.  The status disappears after a few seconds.

#### Setup Status
HouseCurve displays setup information in this area.

#### Plot zoom / scroll
To zoom into a plot, pinch anywhere on the plot area.  The plot can be scrolled left or right with two fingers.

Plot zoom and scroll only change the horizontal frequency axis.  HouseCurve automatically sets the vertical axis of the plots to show the measurement.


### Setup Screen

#### Display Mode
HouseCurve can display measurements to suit a given task.

**Average** mode (default) is used to capture how an audio system sounds in a listening area. Use this mode when tuning the audio system to match a reference curve.

* Measurements are included in an average as they are collected.
* The average measurement is displayed in bold green.
* Individual measurements will appear in faded green.

**History** mode is used to see the effect of an adjustment from a single microphone location. Use this mode for initial audio system setup, such as speaker position or time alignment.

* The most recent measurement is displayed in bold green.  
* Older measurements appear in green and are faded according to age.

#### Smoothing
Smoothing can be applied to measurements to make it easier to see trends in the measurement.  The selection is applied to all measurements and the selected overlay.  To remove smoothing, select None.

#### Coherence Blanking
Coherence blanking hides regions of the measurement, or overlay, that are [low quality](/HOWTO.md#measurement-quality) and should not be used for tuning.  

Blanking occurs wherever the measurement falls below the selected signal to noise ratio (blanking threshold).  To disable blanking, select Off.

This setting also controls the threshold at which HouseCurve will automatically discard measurements.

#### Frequency Scale
The frequency axis can have an Octave or Decade scale.  This setting applies to all plots.

#### Overlay
Overlays are used to display a previous measurement on the plot for comparison.  Available overlays will be displayed in the list.  Select None to disable overlays.

Overlays can be created from the main screen or by tapping + at the top of the Overlay screen.  If an overlay with the same name exists, it can be overwritten.  Overlays can be removed by tapping Edit.

Overlays are created from available measurements based on the [Display Mode](#display-mode).  In Average mode, the average measurement is used.  In History mode, the most recent measurement is used.

When an overlay is created, it will appear underneath the measurement it is based on.  The overlay will remain on the plot for all subsequent measurements.

#### Reference Curve
A [Reference Curve](/HOWTO.md#select-reference-curve) is displayed on the power plot to serve as a guide for [tuning an audio system](/TUNING.md).  

The curve is positioned on the power plot based on the Reference Curve Fit setting.

HouseCurve ships with some common reference curves.  Additional reference curves can be loaded by tapping + at the top of the Reference Curve screen.  Reference curves can be removed by tapping Edit.

#### Reference Curve Fit
By default, the selected Reference Curve is automatically fitted to measurements based on the [Display Mode](#display-mode).  In Average mode, the average measurement is used.  In History mode, the most recent measurement is used.

[Coherence Blanking](#coherence-blanking) also affects how the Reference Curve is positioned.  Portions of the measurement below the blanking threshold are ignored for fitting.

When automatic fitting is disabled, the curve can be manually positioned by setting a desired dB level at 100 Hz.  This is useful when separately adjusting speakers to a common reference level, such as main speakers and a subwoofer.

#### Chirp Channel
Select the channel for the test signal "chirp" sound.  This is used for higher accuracy phase measurements and [subwoofer measurements](/HOWTO.md#subwoofer-measurements).

#### Sweep Channel
Select the channel for the test signal "sweep" sound.  This is used for [subwoofer measurements](/HOWTO.md#subwoofer-measurements)

#### Internal Mic Compensation
The built in iPhone/iPad microphones have a reasonably flat response and are quite acceptable for tuning an audio system.  However, when compared to an external calibrated microphone, they do show some roll off at the extreme ends of the frequency spectrum.  

Internal Mic Compensation applies a moderate boost below 60 Hz and above 16 KHz to measurements made with the built in iPhone/iPad microphone.

#### External Mic Calibration
HouseCurve supports calibrated external microphones.  Available calibrations will be displayed in the list.  Select None to disable calibration.

Microphone calibrations can be loaded tapping + at the top of the External Mic Calibration screen.  Calibrations can be removed by tapping Edit.

[Curve file format](/HOWTO.md#curve-file-format)

#### Stimulus Type
Stimulus Type controls the “sweep” sound used to measure an audio system.

In most cases, the Log Sine Sweep (default) should be used as it will produce measurements with a higher signal to noise ratio.

Pink Noise is provided for interest sake.  Measurements based on pink noise will have a lower signal to noise ratio.

HouseCurve uses coherent averaging.  This has an interesting effect on Pink Noise measurements.  In a sonically treated room, such as one with sound dampening on the walls, Pink Noise noise measurements will closely match Log Sine Sweep measurements.  In a more typical “reflective” room, Pink Noise power measurements tend to be lower above ~2 KHz.  The degree to which the Pink Noise and Log Sine Sweep measurements match is an indication of how “dead” the room is.

