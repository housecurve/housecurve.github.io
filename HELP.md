## How To Use HouseCurve

1. Connect iPhone/iPad to the audio system using AirPlay, Bluetooth or line out (headphone connector).  See [FAQ](/FAQ.md) for more information.
1. Set initial volume to a low setting using the Volume Up / Down buttons on the side of the iPhone/iPad.
1. Tap **Measure** to start measurement process.  HouseCurve will play a test signal through the audio system and measure the frequency response.  This process will take a few seconds.
1. Adjust volume as needed to obtain successful measurements.  Ideally, measurements should be taken at a normal listening level.  Excessive volume levels may degrade accuracy and may increase risk of damage to hearing and/or equipment.
1. Measurements are displayed in green, the reference curve is displayed in yellow with a +/- 3 dB band. When tuning the audio system, the goal is to get the average measurement within the reference band.
1. Collect additional measurements by tapping **Measure again**.
1. To clear the measurements, tap **Reset**.

### Display Modes

HouseCurve can display measurements to suit a given task.  To change the display modes, go to **Setup**.

![](/assets/img/iPhonePlotMarkup.png)

**Average** mode (default) is used to capture how an audio system sounds in a listening area.  Use this mode when tuning the audio system to match a reference curve.  
* Measurements are included in an average as they are collected.
* The average will be displayed in bold green.  Individual measurements will appear in faded green.
* The reference curve is fitted to the average.
* To clear the measurements and reset the average, tap **Reset** once. The average will remain on the plot in purple so that it can be compared to new measurements. Tap **Reset** again to clear it.

**History** mode is used to see the effects of an adjustment from a single microphone location.  Use this mode for initial system setups, such as adjusting subwoofer phase or speaker position.
* The most recent measurement is displayed in bold green, previous measurements are faded according to age.
* The reference curve is fitted to the most recent measurement.

### Recommendations

Try to reduce background noise as this will improve accuracy.

Take many measurements.  Try to cover all the places a listener might be in the listening area.  Try to hold the microphone where a listener’s ears would be located.  The average measurement will cancel out small variances allowing a best-fit tune for the whole listening area.

Tune the audio system in small steps, collecting the same measurements after each change.  When most of the average measurement is within the reference band, the audio system is sufficiently tuned.  Further tuning may not be perceptible.

When using HouseCurve with compensation turned on, the built in iPhone/iPad microphone is accurate enough to get within a few dB of the reference curve.  HouseCurve supports calibrated external microphones for users seeking higher accuracy.  Go to **Setup** to select or load external microphone calibrations.

HouseCurve provides some common reference curves or “house curves”.  The selection of curve is subject to individual taste.  Custom curves may also be imported by going to **Setup**.  When in doubt go with the default curve.

Plot smoothing and frequency scale can be changed at any time by going to **Setup**.

HouseCurve measurements may be affected by iPhone/iPad cases.

