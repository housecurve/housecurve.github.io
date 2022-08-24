---
layout: default

title: Room Correction with miniDSP
parent: App Notes
nav_order: 1
---

# Room Correction with miniDSP

HouseCurve is an iOS application for tuning audio systems.  It can be used for tuning tasks like creating room correction filters, subwoofer time alignment, level matching and choosing crossovers.  A free trial can be found at [housecurve.com](https://housecurve.com).

In this application note, we will demonstrate room correction using HouseCurve and a miniDSP processor.

For an introduction to room correction please read the [overview](https://www.minidsp.com/applications/digital-room-correction/161-digital-room-correction).  To learn more about taking measurements with HouseCurve please see the usage [documentation](https://housecurve.com/USAGE.html).


## What you need

* A miniDSP processor connected to your audio system.
* Plug-in software to configure the miniDSP processor.
* An iPhone or iPad with HouseCurve installed on it.

HouseCurve achieves reasonable measurement accuracy with the built in iPhone or iPad microphones (cases may interfere with microphone).

For additional accuracy, a calibrated measurement microphone can be used, such as the [UMIK-1](https://www.minidsp.com/products/acoustic-measurement/umik-1) or [UMIK-2](https://www.minidsp.com/products/acoustic-measurement/umik-2) (requires a Lightning to USB [adapter](https://www.apple.com/shop/product/MD821AM/A/lightning-to-usb-camera-adapter)).

The procedures below may not exactly apply to your system.  The miniDSP processors are very flexible and can be set up in many different ways.  Fortunately, HouseCurve was designed for rapid experimentation.  We suggest trying the steps below as written and then adjust as needed to suit your own particular situation.


## 1. Get Connected

HouseCurve measures your audio system by listening to it play a sine sweep.  Connect your iPhone or iPad to your audio system using AirPlay, Bluetooth or the headphone jack (using an appropriate [cable](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jack-adapter)).

If direct connection isn’t possible, the sine sweep file can be transferred to the audio system and played manually while HouseCurve listens.  For more information see [connection](https://housecurve.com/docs/usage/connection.html).


## 2. Collect Measurements

Using the miniDSP plug-in software, ensure that all equalization is disabled.

![equalizer set to flat](/assets/img/minidsp_flat.png "measure with equalization disabled")

Launch HouseCurve on your iPhone/iPad.  Tap <img src="/assets/img/reset.png" alt="Reset" class="app-icon"> to clear previous measurements.

![ready to measure](/assets/img/minidsp_ready.png "start with an empty plot")

Tap <img src="/assets/img/plot.png" alt="Plot Setup" class="app-icon"> to display the Plot Setup screen.  Ensure that the plot mode is “average”.

![plot setup](/assets/img/minidsp_plot_setup.png "plot setup screen showing average mode")
{: .app-portrait }

Use HouseCurve to measure your listening area.  Ensure that the microphone is pointed in the direction of the speakers.  Measure at a normal listening volume.

HouseCurve will automatically average measurements as they are collected.  To get a realistic measurement of your [listening area](https://housecurve.com/docs/usage/listening_area.html), it is important to average measurements from several locations.  For a desk (near field), try measuring from 2-3 locations. For a living room, try 3-5 locations.

![averaged measurements](/assets/img/minidsp_average_cursor.png "average measurements to capture listening area")

When you are satisfied with the average measurement, save it by tapping <img src="/assets/img/save.png" alt="Save" class="app-icon">.  This measurement will be used to generate the room correction filters.


## 3. Generate Filters

Tap <img src="/assets/img/more.png" alt="More" class="app-icon"> and select Equalize.  HouseCurve will display the [Equalize](https://housecurve.com/docs/manual/equalize_screen.html) tool.

The Equalize tool generates biquad (IIR) filters to correct a saved measurement to a target curve.  The process is instantaneous, so the display automatically updates to reflect any setting change (target curve, saved measurement, filter settings, etc).

![equalize screen](/assets/img/minidsp_equalized.png "equalize tool creates filers to match saved measurement to target curve")

HouseCurve allocates filters to regions with the largest deviation from the target curve, preferring lower frequencies and ignoring areas with low coherence (SNR).  You can adjust the target curve and coherence blanking threshold by tapping <img src="/assets/img/plot.png" alt="Plot Setup" class="app-icon">.

Tap <img src="/assets/img/setup.png" alt="Equalize Setup" class="app-icon"> to display the Equalize Setup screen.  Check that maximum filters is set to the number supported by your miniDSP processor.

![equalize setup](/assets/img/minidsp_equalize_setup.png "equalize setup controls filter generation")
{: .app-portrait }

Tap <img src="/assets/img/detail.png" alt="Detail" class="app-icon"> to display the individual filters generated by HouseCurve.

![filter detail](/assets/img/minidsp_filter_detail.png "filter detail screen shows individual filter settings")
{: .app-portrait }

## 4. Export Filters

Filters can be exported to a file by tapping <img src="/assets/img/export.png" alt="Export" class="app-icon">.  Ensure that the format is set to “biquad coefficients” and the sample rate is appropriate for your miniDSP processor (ex: 2x4 HD uses 96000 Hz and the DDRC-24 uses 48000 Hz).

![filter export](/assets/img/minidsp_filter_export.png "export filter settings to file")
{: .app-portrait }

Tap ***Export filters***, select a location for the filter file and then tap save.  Choose a location that the miniDSP plug-in software can access (ex: iCloud Drive).  Alternatively, you can choose a location on the iPhone/iPad and then transfer the file using email, AirDrop, iMessage, etc.


## 5. Load Filters

Load the filters into your miniDSP processor using the plug-in software.  Open the PEQ block that you want to put the filters in.  Choose Advanced mode and click on IMPORT.  Select the filter file and click Open.  The plug-in will display the correction filters.

![loaded filters](/assets/img/minidsp_peqs.png "load filter file using miniDSP plug-in software")

Double check that the filter peaks are in the correct location by comparing to HouseCurve’s Equalize tool.  If they appear slightly shifted, it’s likely the filters were created for the wrong sample rate. Repeat the export process with the correct sample rate.


## Wrapping Up

With the filters loaded, you can repeat your original measurements to confirm that your system now matches the target curve.  The average should be reasonably close to the response predicted by HouseCurve.  Happy listening!



