---
layout: default

title: Crossover Frequencies
parent: Tuning
nav_order: 2
---


# Choose crossover frequencies

For audio systems that incorporate limited range speakers, the crossover frequencies need to be selected.

The classic approach is to select crossover frequencies based on speaker specifications, but these may not reflect how the speakers perform in the room.  It is better to measure the actual speaker performance. Use [saved measurements](../manual/plot_setup.md#saved-measurments), to compare speakers and select a crossover frequency.

The screenshot below shows a small 2.1 desktop audio system.  The speakers were measured separately with crossovers disabled and no equalization.  The [subwoofer was measured](../usage/subwoofer.md) first and saved (grey), then the main speakers were measured (green).

![finding crossover frequency](/assets/img/crossover_select.png "Measure speakers separately to find best crossover frequency")

The published frequency range for the main speakers is 80-20000 Hz and the subwoofer is 35-165 Hz.  Based on the specs, the overlap of these speakers is 80 - 165 Hz and the crossover frequency should be somewhere in that range.

On the magnitude plot, we can see the main speaker drops off quickly below ~120 Hz.  For this system the crossover frequency should be somewhere in the 100-120 Hz range.  The subwoofer is more than capable of filling in below 100 Hz.



