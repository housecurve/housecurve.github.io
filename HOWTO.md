## How to use HouseCurve

### Connecting to an audio system
HouseCurve sends test sounds to your audio system and measures the result using a microphone. This is shown in the diagram below.

![](/assets/img/Connecting.png)

HouseCurve can connect wireless to the audio system using AirPlay or Bluetooth. Tap the AirPlay button at the bottom of the screen to see a list of outputs.

Alternatively, the headphone connector can be used to create a wired connection to the audio system.  Use a [Lightning to 3.5mm adapter](https://www.apple.com/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jack-adapter).

HouseCurve will default to using the built in microphone of your iPhone/iPad.  These microphones are quite accurate and are suitable for most tuning tasks.

For additional accuracy, HouseCurve can use external microphones.  It will automatically use an external microphone if one is connected to your iPhone/iPad.

HouseCurve has been tested with the following external calibrated microphones:

* [miniDSP UMIK-1](https://www.minidsp.com/products/acoustic-measurement/umik-1)
* [Dayton Audio iMM-6](https://www.daytonaudio.com/product/1117/imm-6-idevice-calibrated-measurement-microphone)

When CarPlay is used to connect to an automobile audio system, be aware that the selected microphone will be the automobile (head unit) microphone, not the iPhone/iPad microphone.  It may be possible to override this by connecting an external microphone to the automobile.  Alternatively, connect using Bluetooth or the headphone connector.

If you are getting strange measurements, try another microphone.  A common microphone for sanity checks is the [iPhone EarPods with Lighning Connector](https://www.apple.com/shop/product/MMTN2AM/A/earpods-with-lightning-connector).

### Listening area
When listening to an audio system, we hear the combination of the audio system and its surroundings.  In classic audio speak, the surroundings are referred to as “the room” regardless of what they actually are (ex: living room, office, automobile, outdoor patio).

When sound leaves an audio system it interacts with the room and this changes the sound.  This interaction is complex.  It depends on the frequency of the sound, the dimensions of the room and how the room is constructed.  In addition, and most importantly, it depends on the location in the room.

The first step in tuning an audio system is to establish a listening area.  Where in “the room” do you want it to sound good?  This could be a couch, a desk, or a kitchen.  Think about where the listeners ears will be most of the time.  This is the listening area.


### Measurement process
A single measurement represents how the audio system sounds at a single location.  To get a realistic measurement of the listening area, it is important to **take measurements from several locations**.  For a desk (near field), try 2-3 locations.  For a living room, try 3-5 locations.  Aim the microphone towards the audio system.  These measurements can be averaged so that small variances cancel out making it possible to find a “best fit” tune for a given listening area.

The measurement process starts when the [Measure](/MANUAL.md#measure) button is pressed.  HouseCurve will play a test signal through the audio system.  This signal consists of a “chirp” sound followed by the the stimulus “sweep” sound.  The chirp is a timing reference that tells HouseCurve when to expect the sweep sound.  The sweep sound is used to measure the audio system.

The stages of the measurement process are displayed in the [Measurement Status](/MANUAL.md#measurement-status) area at the top of the screen.

![](/assets/img/Listening.png)

When a measurement succeeds it will be displayed on the plots as shown below. 

![](/assets/img/Success.png)

HouseCurve will abort the measurement process for the following reasons:

**Could not detect test signal**  If HouseCurve is unable to detect the chirp signal after about 10 seconds, it will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the chirp, but it does not need to be loud.
* If you can hear the chirp sound, check that the microphone is not obstructed.  Cases for iPhone/iPads can obstruct the microphone.  Be sure to aim the microphone at the audio system and ensure it’s not covered up by your hand (ex: Bottom of iPhone).
* If using an external microphone, ensure the cabling is connected properly.  Try disconnecting and using the built in iPhone/iPad microphone instead.

**Low measurement coherence**  After the chirp is detected, HouseCurve records the sweep as it is played by the audio system.  If the recorded sweep has a very low signal to noise ratio, HouseCurve will abort the measurement.  If this happens, check the following:

* Ensure the audio system or iPhone/iPad volume is set to a normal listening level.  You should be able to clearly hear the sweep, but it does not need to be loud.
* Take steps to reduce background noise.  HouseCurve works best when measurements are taken from a quiet listening area.
* Lower the [Coherence Blanking](/MANUAL.md#coherence-blanking) threshold.


### Measurement quality
When [Coherence Blanking](/MANUAL.md#coherence-blanking) is enabled, only portions of the measurement that are above the selected signal to noise ratio will be displayed.  This is a helpful indicator of measurement quality.  

For example, the measurement below was taken in the presence of external noise (someone talking).  This significantly contaminated the measurement and unusable sections have been blanked.  This measurement should probably be discarded.

![](/assets/img/LowCoherence.png)

Signal to noise issues are typically resolved by removing sources of noise or increasing the volume of the audio system.  In rare situations the microphone may be faulty.


### Plots
HouseCurve displays successful measurements on the power, phase and group delay plots.  Use the Page Control to switch between plot types, or swipe from the left/right edge of the screen.

The **power plot** is the most important plot for tuning.  The overall level of the power measurement is the “volume” of the audio system.  The level differences between frequencies is what we want to change when [adjusting an equalizer](/TUNING.md#apply-equalization).

![](/assets/img/Power.png)

The power plot is commonly referred to as the “frequency response” of the audio system.  It may also be referred to as the “magnitude” plot, which is identical to the power plot as long as they are both displayed in decibels.

The **phase plot** shows the phase of the measurement versus frequency.  Phase plots can be used for [time aligning speakers](/TUNING.md#time-align-using-phase).

![](/assets/img/Phase.png)

This style of phase plot is traditionally referred to as a “wrapped phase” plot.  The vertical green lines on the plot are referred to as “wraps”.  A wrap is a frequency where the phase exceeds the range of the plot and “wraps” around to the other vertical extreme of the plot.  A wrap is an artifact of the plot and not and indication that the phase is suddenly changing by 360 degrees.

The **group delay plot** shows “when” the sound at a given frequency arrives at the microphone.  The group delay plot can be used to double check [speaker time alignment](/TUNING.md#time-align-speakers).  Extreme peaks in the group delay may indicate regions that can’t be fixed by equalization, such as poor time alignment or problematic room interactions.

![](/assets/img/Delay.png)


### Subwoofer measurements
A subwoofer (or woofer) lacks the frequency range to play the chirp sound of the test signal (see [measurement process](#measurement-process)).  To measure a subwoofer with HouseCurve, another full range speaker is needed to produce the chirp and serve as the timing reference.

HouseCurve can be configured to play the chirp and sweep sounds on [different audio channels](/MANUAL.md#chirp-and-sweep-channel).  This makes it possible to route the sweep to the subwoofer and the chirp to another speaker (typically a main or center speaker).  Not all audio systems will support this.

For a typical 2.1 audio system, this can be accomplished by disabling (or disconnecting) a main speaker, ex: the right speaker.  HouseCurve is then configured to play the sweep through the right channel and the chirp through the left channel.  The subwoofer will receive the right channel via the “subwoofer out” of the audio system.  This is pictured below:

![](/assets/img/SubwooferSweep.png)

Use [Coherence Blanking](/MANUAL.md#coherence-blanking) to ensure the plots only show portions of the measurement that are actually from the subwoofer and not simply noise.  The plot below shows a subwoofer measurement with Coherence Blanking turned off.  As can be seen, the plot shows a peak where the subwoofer is actually able to produce sound.  The rest of the measurement is the noise floor of the audio system and room.

![](/assets/img/SubNoBlanking.png)

Below the same measurement is shown with Coherence Blanking set to 50%.  Now only the useful portion of the measurement is shown.

![](/assets/img/SubBlanking.png)

When separately adjusting main and subwoofer speakers to the same Reference Curve, it is recommended that the [Reference Curve Fit](/MANUAL.md#reference-curve-fit) setting be switched to manual and a suitable level entered.  The Reference Curve will then appear at the same level for all measurements.  In the examples above, the Reference Curve was fixed at 24.5 dB @ 100 Hz.


### Curve file format

HouseCurve supports the following file format for reference curves and microphone calibrations: 

A space or tab delimited text file with a frequency (Hz) followed by a gain (dB) on each line. A third phase value may be included but is ignored. Lines starting with non-numeric characters are ignored. Frequencies must be listed in increasing order. HouseCurve will interpolate a curve from 20-20000 Hz using the values provided. The file extension may be txt or frd.

[Example Reference Curve](/examples/curve.txt)

HouseCurve is able to load files from iPhone/iPad local storage and iCloud.  To load a curve file from a website, save it to the iPhone/iPad storage and then select from within HouseCurve.

