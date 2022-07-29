---
layout: default

title: Equalize Setup
parent: Manual
nav_order: 6
---

# Equalize Setup
The Equalize Setup screen can be accessed by tapping <img src="/assets/img/setup.png" alt="Setup" class="app-icon"> on the Equalize screen.

![Equalize setup screen](/assets/img/equalize_setup.png)
{: .app-portrait-right }

## Maximum filters
The number of filters to use for correction.

Set this to the number of filters your parametric equalizer supports.  HouseCurve may not use all the filters.  HouseCurve currently only supports peaking filters (no shelving filters, etc.  If you would find this useful, please [reach out](mailto:support@housecurve.com)).

## Frequency
The frequency range to equalize.  

Use the minimum frequency to prevent the algorithm from correcting low frequencies beyond the capabilities of the audio system, ex: trying to boost at 20 Hz when the audio system can barely produce 40 Hz at -6 dBFS.  Doing so will lead to distortion and possibly audio system damage.

The maximum frequency can be used to avoid wasting filters on high frequency issues that may not be audible.

## Gain
The gain range for filters (absolute gain).

Use the minimum gain to prevent the creation of very small (and likely inaudible) filters.

The maximum gain limits the size of a boost or a cut an individual filter can make.  HouseCurve may place filters in close proximity to produce larger gains.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more signal power.



