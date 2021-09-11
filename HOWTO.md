## How to use HouseCurve

### Connecting to an audio system
HouseCurve sends test sounds to your audio system and measures the result using a microphone. This is shown in the diagram below.

![](/assets/img/Connecting.png)

HouseCurve can connect wireless to the audio system using AirPlay or Bluetooth. Tap the AirPlay button at the bottom of the screen to see a list of outputs.

Alternatively, the headphone connector can be used to create a wired connection to the audio system.  Use a Lightning to 3.5mm adapter.

HouseCurve will default to using the built in microphone of your iPhone/iPad.  These microphones are quite accurate and are suitable for most tuning tasks.

For additional accuracy, HouseCurve can use external microphones.  It will automatically use an external microphone if one is connected to your iPhone/iPad.

HouseCurve has been tested with the following external calibrated microphones:

* https://www.minidsp.com/products/acoustic-measurement/umik-1
* https://www.daytonaudio.com/product/1117/imm-6-idevice-calibrated-measurement-microphone

When CarPlay is used to connect to an automobile audio system, be aware that the selected microphone will be the automobile (head unit) microphone, not the iPhone/iPad microphone.  It may be possible to override this by connecting an external microphone to the automobile.  Alternatively, connect using Bluetooth or the headphone connector.


### Listening area
When listening to an audio system, we hear the combination of the audio system and its surroundings.  In classic audio speak, the surroundings are referred to as “the room” regardless of what they actually are (ex: living room, office, automobile, outdoor patio).

When sound leaves an audio system it interacts with the room and this changes the sound.  This interaction is complex.  It depends on the frequency of the sound, the dimensions of the room and how the room is constructed.  In addition, and most importantly, it depends on the location in the room.

The first step in tuning an audio system is to establish a listening area.  Where in “the room” do you want it to sound good?  This could be a couch, a desk, or a kitchen.  Think about where the listeners ears will be most of the time.  This is the listening area.


### Measurement process
A single measurement represents how the audio system sounds at a single location.  To get a realistic picture of how the listening area sounds, it is important to **take measurements from several locations**.  These measurements can be averaged so that small variances cancel out making it possible to find a “best fit” tune for a given listening area.

The measurement process starts when the [Measure](/MANUAL.md#measure) button is pressed.  HouseCurve will play a test signal through the audio system.  This signal consists of a “chirp” sound followed by the the stimulus “sweep” sound.  The chirp is a timing reference that tells HouseCurve when to expect the sweep sound.  The sweep sound is used to measure the audio system.

The stages of the measurement process are displayed in the Measurement Status area at the top of the screen.

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
* Lower the [Coherence Blanking](/Manual.md#coherence-blanking) threshold.

### Measurement quality

### Plots

### Subwoofer measurements

### Curve file format


