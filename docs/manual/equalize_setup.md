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

When PEQ is selected, HouseCurve will generate a set of parametric equalizer filters (peaking biquad filters).  These can be exported as PEQ settings, biquad coefficients or converted into an impulse response.

When FIR is selected, HouseCurve will generate a mixed phase FIR filter.  FIR filters are exported as impulse responses.

## Frequency
The frequency range to equalize.  

Use the minimum frequency to prevent the algorithm from correcting low frequencies beyond the capabilities of the audio system, ex: trying to boost at 20 Hz when the audio system can barely produce 40 Hz at -6 dBFS.  Doing so will lead to distortion and possibly audio system damage.

The maximum frequency can be used to avoid wasting filters on high frequency issues that may not be audible.

## Max gain
The maximum gain range filters (absolute gain).

The maximum gain limits the size of a boost or a cut an individual filter can make.  HouseCurve may place filters in close proximity to produce larger gains.  Keep in mind that a +10 dB adjustment means the audio system has to output 10 times more signal power.

## Allow only cuts
Prevents the creation of filters with positive gain (boost) to avoid clipping.  Use manual [curve fit](../manual/plot_setup.md#target-curve-fit) to lower the target curve and improve the overall correction without using boost.

## Max filters
The maximum number of filters to use for PEQ correction.  HouseCurve will allocate filters until the remaining corrections are outside of the frequency and gain settings.

For a parametric equalizer, set this to the number of filters your system supports.  For a convolution engine (ie: using the impulse response), the number of filters just controls the fidelity of the correction.  More filters may not make an audible difference.

## Max Q
The maximum Q for PEQ filters, set this to the value your parametric equalizer supports.  The "Q" of a filter is roughly the width.  The higher the Q, the narrower the filter.


