---
layout: default

title: Room Correction with Volumio
parent: App Notes
nav_order: 3
---

# Room Correction with Volumio

[Volumio](https://volumio.com) is open source music playback software that can run on a PC, Raspberry Pi, etc.  It provides DSP features through a plugin called FusionDSP, which is a front end for [CamillaDSP](https://github.com/HEnquist/camilladsp).

HouseCurve is an iOS application for tuning audio systems.  It turns your iPhone/iPad into a capable audio analyzer using the built in microphone.  It can be used for tuning tasks like creating room correction filters, subwoofer time alignment, level matching and choosing crossovers.  A free trial can be found at [housecurve.com](https://housecurve.com).

This app note will demonstrate room correction using HouseCurve and Volumio's FusionDSP plugin.

For an introduction to room correction, please read the [overview](../tuning/equalization.md#what-is-equalization--room-correction).  To learn more about taking measurements with HouseCurve please see the usage [documentation](../usage/USAGE.md).


## What you need

* An audio system running Volumio 3 with the FusionDSP plugin.
* A Volumio control (web interface, dedicated app, etc).
* An iPhone or iPad with HouseCurve installed on it.

HouseCurve achieves reasonable measurement accuracy with the built in iPhone or iPad microphones.  For more information see [microphones](../usage/microphones.md).

You will need a way to transfer files from your iPhone/iPad to Volumio.  Use whatever method you are most comfortable with.  This app note will use Volumio's `/mnt/INTERNAL` Samba share (comes configured in the Raspberry Pi image).

Samba on Linux doesn't always work with iOS devices.  To ensure compatibility, install the [Fruit](https://www.samba.org/samba/docs/current/man-html/vfs_fruit.8.html) Samba VFS module.  Without this, file transfers may fail with "attribute not found" errors.  For instructions [see](https://apple.stackexchange.com/questions/424681/the-operation-couldnt-be-completed-operation-canceled-error-message-when-sa).

For best results, ensure the audio system is [set up correctly](../tuning/TUNING.md) before applying room correction.


## 1. Install FusionDSP Plugin

Using the Volumio control, install the plugin by going to Volumio settings -> plugins.  You will need to sign your device into a MyVolumio account (free or paid) to see the plugin.

![FusionDSP Plugin](/assets/img/volumio_plugin.png "plugin installed")
{: .app-portrait }


## 2. Get Connected

HouseCurve measures your audio system by listening to it play a sine sweep test signal.  There are several way
s to do this as described in [connecting](../usage/connecting.md).

For this app note, we will perform measurements using [externally played sweeps](../usage/connecting.md#externally-played-sweeps).  This method doesn't require a direct connection to the audio system.  Instead, we transfer the test signal as a wav file to the audio system and play it manually.  HouseCurve will measure by listening to the test signal as it is played.

This method will work with any audio system, but it requires more steps.  You can skip this and use a direct connection instead, see [connecting](../usage/connecting.md) for more infomration.  Note - at the time of writing this app note, measurements over AirPlay didn't work with Volumio on a Raspberry Pi 3B.  This isn't uncommon for unofficial AirPlay implementations (Shairport-sync, etc).

To transfer files to Volumio's Samba share, open up the [Files](https://apps.apple.com/ca/app/files/id1232058109) app on you iPhone/iPad and select ***Connect to Server***.  Enter the network name of the Volumio device (ex: volumio.local) and connect as a Guest.  HouseCurve will now be able to save to this location.

![Volumio samba share](/assets/img/volumio_connect_server.png "connect to server as guest")
{: .app-portrait }

Launch HouseCurve on your iPhone/iPad.  Tap <img src="/assets/img/setup.png" alt="Setup" class="app-icon"> to display the Measure Setup screen, then tap ***Stimulus Type***.

![measure setup](/assets/img/volumio_measure_setup.png "measure setup")
{: .app-portrait }

Set the stimulus type to  ***External Sine Sweep***.  Tap ***Export test signal*** and select a location to save the wav file and transfer to Volumio's library.

![stimulus type](/assets/img/volumio_stimulus_type.png "select external sine sweep and export test signal")
{: .app-portrait }

If you save directly to Volumio's Samba share, you will need to refresh the library to see the file.

![Saving to share](/assets/img/volumio_save_signal.png "saving directly to Volumio's library")
{: .app-portrait }

You should now be able to play the test signal using Volumio.


## 3. Collect Measurements

Using the Volumio control, access the FusionDSP plugin and ensure that equalization is disabled.

Launch HouseCurve on your iPhone/iPad.  Tap <img src="/assets/img/reset.png" alt="Reset" class="app-icon"> to clear previous measurements.

![ready to measure](/assets/img/volumio_ready.png "start with an empty plot")

Tap <img src="/assets/img/plot.png" alt="Plot Setup" class="app-icon"> to display the Plot Setup screen.  Ensure that the plot mode is “average”.

![plot setup](/assets/img/volumio_plot_setup.png "plot setup screen showing average mode")
{: .app-portrait }

To measure with external sweeps, first tap <img src="/assets/img/measure.png" alt="Plot Setup" class="app-icon"> on HouseCurve to start the measurement process.  Then use Volumio to play back the test signal.  Ensure that the iPhone/iPad microphone is pointed in the direction of the speakers.  Measure at a normal listening volume.

Note - HouseCurve must remain in the foreground to measure.  If you need to trigger playback with the same iPhone/iPad, start a looped playback, then switch back to HouseCurve to start the measurement.  HouseCurve will only collect one measurement at a time.

![Looped playback](/assets/img/volumio_looped.png "play the test signal on repeat")
{: .app-portrait }

HouseCurve will automatically average measurements as they are collected.  To get a realistic measurement of your [listening area](../usage/listening_area.md), it is important to average measurements from several locations.  For a desk (near field), try measuring from 2-3 locations. For a living room, try 3-5 locations.

![averaged measurements](/assets/img/volumio_average.png "average measurements to capture listening area")

When you are satisfied with the average measurement, save it by tapping <img src="/assets/img/save.png" alt="Save" class="app-icon">.  The saved measurement will be used to generate the room correction filters.


## 4. Generate Filters

Tap <img src="/assets/img/more.png" alt="More" class="app-icon"> and select Equalize.  HouseCurve will display the [Equalize](../manual/equalize_screen.md) tool.

The Equalize tool generates biquad (IIR) filters to correct a saved measurement to a target curve.  These filters can be exported as parametric equalizer settings, which is what we will use in this app note (FusionDSP also supports the impulse response (FIR filter) exported by HouseCurve).

The generation process is instantaneous, so the display automatically updates to reflect any setting change (target curve, saved measurement, filter settings, etc).

![equalize screen](/assets/img/volumio_equalized.png "equalize tool creates filters to match saved measurement to target curve")

HouseCurve allocates filters to regions with the largest deviation from the target curve, preferring lower frequencies and ignoring areas with low coherence (SNR).  You can adjust the target curve and coherence blanking threshold by tapping <img src="/assets/img/plot.png" alt="Plot Setup" class="app-icon">.

Tap <img src="/assets/img/setup.png" alt="Equalize Setup" class="app-icon"> to display the [Equalize Setup](../manual/equalize_setup.md) screen.  The default settings should provide a good correction, but feel free to experiment.

![equalize setup](/assets/img/volumio_equalize_setup.png "equalize setup controls filter generation")
{: .app-portrait }


## 5. Export Filters

Filters can be exported to a file by tapping <img src="/assets/img/export.png" alt="Export" class="app-icon">.  Ensure that the format is set to “Parametric EQ Settings".  For more information on the format, see [file formats](../manual/file_formats.md#parametric-eq-settings).

![filter export](/assets/img/volumio_filter_export.png "export filter settings to file")
{: .app-portrait }

Tap ***Export filters***, select a location for the filter file and then tap save.  The filter file must be placed in `/mnt/INTERNAL/FusionDSP/peq` for FusionDSP to see it.  Using Volumio's Samba share, you can save directly to this location:

![save filter](/assets/img/volumio_save_filters.png "save filter to peq folder")
{: .app-portrait }


## 6. Load Filters

Using the Volumio control, go to the settings for the FusionDSP plugin.  Set ***Type of DSP*** to "Parametric equalizer" and apply the setting.

![Use Parametric EQ](/assets/img/volumio_peq.png "switch FusionDSP to Parametric EQ")
{: .app-portrait }

Scroll down to the section labelled ***Import A Local EQ File***.  Select the filter file and press load.  If the filter isn't available in the drop down, make sure it was placed in `/mnt/INTERNAL/FusionDsp/peq`.

![Load Filter](/assets/img/volumio_import_filters.png "import filters")
{: .app-portrait }

The filters will be loaded and enabled immediately. Scroll back up to the ***Settings*** section to see the loaded filters.  You may need to adjust the automatic preamp / gain settings to match the original playback levels.  Volumio seems to lower the overall gain when filters are loaded.


## Wrapping up

With the filters loaded, you can repeat the original measurements to confirm that your system now matches the target curve.  The average should be reasonably close to the response predicted by HouseCurve.  Happy listening!




