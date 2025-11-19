---
layout: default

title: Filter Export
parent: Manual
nav_order: 11
---

# Filter Export
The Filter Export screen can be accessed by tapping <img src="/assets/img/export.png" alt="Export" class="app-icon"> on the Equalize screen.

![Filter export screen](/assets/img/filter_export.png)
{: .app-portrait-right }

## Format
The format used to export the filters.  This setting is hidden when the [filter type](../manual/equalize_setup.md#filter-type) is set to FIR.

Biquad Coefficients, Parametric EQ Settings, Impulse Response - These are file based [filter formats](file_formats.md#filters).  When export is tapped a screen will appear asking where to save the file, ex: iCloud drive.

Crestron DM NAX - Uploads filters to a [Crestron&reg; DM NAX](https://www.crestron.com/Products/Featured-Solutions/Audio-Over-IP) device.  When export is tapped, a connection screen will appear asking for the device IP address and login credentials (same as [web interface](https://docs.crestron.com/en-us/9045/Content/Topics/DM-NAX-8ZSA/Configure-8ZSA.htm#Access_the_Web_Interface_with_a_Web_Browser)).  Choose a zone and tap upload.  To clear filters, choose a zone and tap reset.  Changes take effect immediately.


## Sample Rate
The sample rate for the exported filter (ie: rate used by equalizer).  Choose "all" to export for all supported sample rates.  This setting is hidden for formats that don't require a sample rate.

## Export
Tap to initiate the file export.


