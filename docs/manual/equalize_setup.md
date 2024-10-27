---
layout: default

title: Equalize Setup
parent: Manual
nav_order: 7
---

# Equalize Setup
The Equalize Setup screen can be accessed by tapping <img src="/assets/img/equalize_setup.png" alt="Setup" class="app-icon"> on the Equalize screen.

![Equalize setup screen](/assets/img/equalize_setup_screen.png)
{: .app-portrait-right }

## Filter type
Selects the type of filter HouseCurve will use to produce a correction.

When PEQ is selected, HouseCurve will generate a set of peak filters.  These can be exported as PEQ settings, biquad coefficients or converted into an impulse response.

When FIR is selected, HouseCurve will generate a mixed phase FIR filter.  FIR filters are exported as impulse responses.

## Frequency
The frequency range to equalize.  

Adjust the frequency range to match the capabilties of your audio system.  Attempting to correct beyond its capabilities will lead to distortion and possibly audio system damage.  For example, if your system is -10 dB below the target curve at 40 Hz, it is unlikely a 10 dB boost will improve the bass without distortion.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more power. 

Lower the maximum frequency to avoid wasting filters on issues that may not be audible.  This also helps Equalize Tool focus on the lower frequencies, where room correction has the largest benefit.

## Max gain
The maximum boost or cut an individual filter can make.

Equalize Tool may place PEQ filters in close proximity to produce a boost that exceed the maximum.  If this happens, the maximum boost will be displayed in red (see: [equalize status](../manual/equalize_tool.md)).

## Allow only cuts
Prevents the creation of filters with positive gain (boost) to avoid clipping.  Use manual [curve fit](../manual/plot_setup.md#target-curve-fit) to lower the target curve and improve the overall correction without using boost.

## Max filters
The maximum number of filters to use for PEQ correction.  HouseCurve will allocate filters until the remaining corrections are outside of the frequency and gain settings.

For a parametric equalizer, set this to the number of filters your system supports.  For a convolution engine (ie: using the impulse response), the number of filters just controls the fidelity of the correction.  More filters may not make an audible difference.

## Max Q
The maximum Q for PEQ filters.  Set this to the value your parametric equalizer supports.  The minimum Q is fixed at 0.5.  The "Q" of a peak filter is roughly the width.  The higher the Q, the narrower the filter.

## Allow shelf filters
When enabled, Equalize Tool will consider high shelf and low shelf filters in the correction.  In some cases, a single shelf filter can replace several peak filters, resulting in a better correction.

The Q range for shelf filters is limited to between 0.5 and 1.0.  This ensures the shelf filters smoothly raise or lower regions.  At Q values above 1.0, the smooth shape of the shelf begins to degenerate, growing peaks on either side of the center frequency (a boost and a cut).


