---
layout: default

title: Main Menu
parent: Manual
nav_order: 1
---

# Main Menu
Use the HouseCurve main menu to access different tools.

![main menu](/assets/img/main_menu.png "HouseCurve Main Menu")
{: .app-portrait-right }

## Sweep
The [Sweep tool](sweep_tool.md) measures your audio system with logarithmic sine sweeps.

A sine sweep produces a better measurement than pink noise because it concentrates the signal power at one frequency at a time.  The resulting measurement has a higher signal to noise ratio.

The drawback to sweeps is they can't be used in real time, ex: to see the effect of tuning.  Tuning with sine sweeps requires repeated measure-adjust-measure steps.  Multiple sweep measurements must be averaged to capture the average sound of a listening area.

Single sine sweep measurements are included in the free version of HouseCurve.  With the [Tuning Bundle](../DOWNLOAD.md#tuning-bundle), measurements can be averaged or compared, and phase and group delay plots are available.

## Real Time
The [Real Time tool](realtime_tool.md) measures your audio system with pink noise.

Pink noise spreads signal power over the entire audible range.  This means pink noise measurements will have a lower signal to noise ratio comared to sweeps.

The advantage of pink noise is that it can be used in real time.  This makes it possible to see the measurement change as an adjustment is being made, ex: moving a graphic EQ slider.  Pink noise measurements are also handy to quickly capture an average measurement of a listening area by simply moving the microphone (aka: "moving mic measurements", or MMM).

## Equalize
The [Equalize tool](equalize_tool.md) generates room correction filters using a saved measurement and a target curve.

## Curve Edit
Use the [Curve Editor](curve_edit.md) to create a target curve of your liking.  Curves can be created by dragging and droppging points, or the points can be entered as text into the source editor (an easy way to cut and paste a target curve from the internet).

## Measurements
The [Measurements tool](measurements_tool.md) is an organizer for saved measurements.  Use it to delete or export measurements.  In the future this tool will also support comparison, etc.

## Help
Help includes links to help topics, contact info and Tuning Bundle subscription status.

