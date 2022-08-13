---
layout: default

title: File Formats
parent: Manual
nav_order: 8
---


# Curve file format

HouseCurve supports the following file format for target curves and microphone calibrations: 

A space or tab delimited text file with a frequency (Hz) followed by a gain (dB) on each line. A third phase value may be included but is ignored. Lines starting with non-numeric characters are ignored. Frequencies must be listed in increasing order. HouseCurve will interpolate a curve from 20-20000 Hz using the values provided. The file extension may be txt or frd.

[Example Target Curve](/curves/curve.txt)

HouseCurve is able to load files from iPhone/iPad local storage and iCloud.  To load a curve file from a website, save it to the iPhone/iPad storage and then select from within HouseCurve.

