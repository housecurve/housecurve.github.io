---
layout: default

title: miniDSP Room Correction
parent: App Notes
nav_order: 1
---

# Room Correction with HouseCurve

[HouseCurve](https://housecurve.com) is an iOS application for tuning audio systems.  It can be used for many tuning tasks such as room correction, subwoofer time alignment, level matching and choosing crossovers.  A free trial can be found at housecurve.com.

In this application note we will demonstrate room correction using HouseCurve and a miniDSP processor.

If you are unfamiliar with room correction please read the [overview](https://www.minidsp.com/applications/digital-room-correction/161-digital-room-correction).

If you are unfamiliar with taking measurements with HouseCurve please see the usage [documentation](https://housecurve.com/USAGE.html).


## What You Will Need

* A miniDSP processor [link?] connected to your audio system
* Plug-in software to configure the miniDSP processor [link?]
* An iPhone or iPad with HouseCurve installed on it.

HouseCurve is able to achieve reasonable accuracy with the built in iPhone or iPad microphones.  Note that cases may interfere with microphone measurements.

For additional accuracy, a calibrated measurement microphone can be used, such as the [UMIK-1](https://www.minidsp.com/products/acoustic-measurement/umik-1) or [UMIK-2](https://www.minidsp.com/products/acoustic-measurement/umik-2) (requires a Lightning to USB [adapter](https://www.apple.com/shop/product/MD821AM/A/lightning-to-usb-camera-adapter)).

*** image of HouseCurve on ipad with mic ***

The miniDSP processors are very flexible and there are a lot of ways they can be set up, so the procedure below might not apply exactly to your system.  Likewise, HouseCurve is also flexible.  It was designed for rapid experimentation with audio systems.  We suggest trying the steps below as written and then adjust as needed to suit your own particular situation.


## 1. Get Connected

HouseCurve measures your audio system by listening to it play a sine sweep.  HouseCurve can connect directly to your audio system using AirPlay, Bluetooth or the headphone jack (with an appropriate [cable](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jack-adapter)).

If direct connection isn’t possible, the sweep file can be transferred to the audio system and played manually while HouseCurve listens.  For more information see [connection](https://housecurve.com/docs/usage/connection.html).


## 2. Collect Measurements

Using the miniDSload filter file using miniDSP plug-in software")
Set HouseCurve’s display mode to “average”.

![plot setup](/assets/img/minidsp_plot_setup.png "plot setup screen showing average mode")
{: .app-portrait-small }

Use HouseCurve to measure your listening area.  Ensure that the microphone is pointed in the direction of the speakers.

To get a realistic measurement of the listening area, it is important to average measurements from several locations.  Averaging provides HouseCurve with a better picture of how sound changes over the listening area.  For a desk (near field), try measuring from 2-3 locations. For a living room, try 3-5 locations.

![averaged measurements](/assets/img/minidsp_average_cursor.png "average measurements to capture listening area")

When you are satisfied with the average measurement, save it by tapping <img src="/assets/img/save.png" alt="Save" class="app-icon">.  This measurement will be used to generate the room correction filters.


## 3. Generate Filters

HouseCurve’s [Equalize](https://housecurve.com/docs/manual/equalize_screen.html) tool generates IIR filter settings for parametric equalizers.  It works by correcting a saved measurement to a target curve.  The filter generation process is instantaneous, so the display automatically updates to reflect any setting change (target curve, saved measurement, filter settings, etc).

![equalize screen](/assets/img/minidsp_equalized.png "equalize tool creates filers to match saved measurement to target curve")

HouseCurve allocates filters to regions with the largest deviation from the target curve, preferring lower frequencies and ignoring areas with poor SNR (low coherence).  You can adjust the target curve and coherence blanking threshold by tapping <img src="/assets/img/plot.png" alt="Plot Setup" class="app-icon">.

Ensure that HouseCurve uses the correct number of filters (PEQs) supported by your miniDSP processor by going tapping <img src="/assets/img/setup.png" alt="Equalize Setup" class="app-icon">.

![equalize setup](/assets/img/minidsp_equalize_setup.png "equalize setup controls filter generation")
{: .app-portrait-small }

The individual filter parameters can be viewed by tapping <img src="/assets/img/detail.png" alt="Detail" class="app-icon">.

![filter detail](/assets/img/minidsp_filter_detail.png "filter detail screen shows individual filter settings")
{: .app-portrait-small }

## 4. Export Filters

Filters can be exported to a file by tapping <img src="/assets/img/export.png" alt="Export" class="app-icon">.  Ensure that the selected format is “biquad coefficients” and that the sample rate is appropriate for your miniDSP processor (ex: 2x4 HD uses 96000 Hz and the DDRC-24 uses 48000 Hz).

![filter export](/assets/img/minidsp_filter_export.png "export filter settings to file")
{: .app-portrait-small }

Press ***Export filters***, select a location for the filter file and then tap save.  Ideally, choose a location that the miniDSP plug-in software can access (ex: iCloud Drive).  Alternatively, you can choose a location on the device and transfer via email, AirDrop, iMessage, etc.


## 5. Load Filters

Load the filters into your miniDSP processor using the miniDSP plug-in.  Open the PEQ block that you want to put the filters in.  Choose Advanced mode and click on IMPORT.  Select the filter file, click PROCESS and the plugin will display the correction filter

![loaded filters](/assets/img/minidsp_peqs.png "load filter file using miniDSP plug-in software")

Double check that the filter peaks are in the correct location by comparing to HouseCurve’s Equalize screen.  If they appear slightly shifted, it’s likely the filters were created for the wrong sample rate.  To correct, re-export the filters with the correct sample rate.


## Wrapping Up

With the filters loaded, you can repeat your original measurements to confirm that your system now matches the target curve.  The average should be reasonably close to response predicted by HouseCurve.  Happy listening!



