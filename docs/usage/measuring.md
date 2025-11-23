---
layout: default

title: Measuring
parent: Usage
nav_order: 3
---

# Measuring
When we listen to an audio system, we hear the combination of the audio system and its surroundings.  In the audio world, the surroundings are referred to as “the room”.  It doesn’t really matter what the surroundings are, living room, auditorium, car, we still call it “the room”.

When sound leaves an audio system it interacts with the room and this changes the sound.  This interaction is complex.  It depends on the frequency of the sound, the dimensions of the room and how the room is constructed.  In addition, and most importantly, it depends on the location in the room.


## Listening area
The first step in tuning an audio system is to establish a listening area.  Where in “the room” do you want it to sound good?  This could be a couch, a desk, or a kitchen.  Think about where the listeners ears will be most of the time.  This is the listening area.


## Single Measurements
A measurement from a single location in the listening area *only* represents that location.  A measurement from a different location will have different peaks and dips.  This can be easily seen by taking sweep measurements from either end of the listening area and comparing them.

Single measurements should not be used for tuning tasks like equalization.  However, they can be used for tasks like [time aligning](../tuning/time_align.md) speakers, picking [crossovers](../tuning/crossover.md) or [matchign levels](../tuning/match_levels.md).


## Average Measurements
Since the goal is to make the whole listening area sound good, we should tune to average measurements taken from the listening area.  An average will cancel out all variances between measurements, providing an "average listening experience" that can be used for tuning.  This is particularly important for wide band adjustments such as [applying equalization](../tuning/equalization.md).

### Averaging sweeps
The Sweep tool can be used to collect average measurments by setting the plot mode to [average](../manual/plot_setup.md#sweep).  Each time a measurement is captured, it will automatically be added to the average.

For a desk (near field), try measuring from 3-5 locations.  For a living room, try 3-7 locations.  Ensure the mic is aimed at the audio system for each measurement.  The exact pattern to use will take some experimentation.  For starts, try measuring along a line that faces the speakers, ex: left, center-left, center, center-right, right.

Averaging with the Sweep tool is more time consuming, but it produces averages for magnitude, phase and group delay.  Decibel averaging is used for magnitudes.  Vector averaging is used for phase.  Arithmetic averaging is used for group delay.

### Moving mic measurements
The Real Time tool provides a faster way to capture a listening area average: Moving Microphone Measurements or MMM.  The trade off is this measurement only captures the magnitude.

To perform a moving mic measurement, set the plot mode to [average](../manual/plot_setup.md#real-time).  Start a measurement and while aiming the mic at the audio system move the mic throug the listening area.  Try to trace a symmetric path ensuring the mic spends equal times on the left and right side of the listening area.  When complete, stop measuring.  It will take some experimentation to find a pattern of movement that works best.





