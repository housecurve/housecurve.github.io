## FAQ

### Where can I use HouseCurve?
If you can connect your iOS device to the audio system, HouseCurve will work.  It has been used for tuning home stereos, televisions and cars. 

### How do I connect HouseCurve to my audio system?

HouseCurve sends a test sound to your audio system and measures the result using a microphone.

![](/assets/img/Connections.png)

The simplest way to connect HouseCurve to your audio system is to use a Lightning to 3.5mm headphone jack [adapter](https://www.apple.com/ca/shop/product/MMX62AM/A/lightning-to-35mm-headphone-jack-adapter).

HouseCurve can also send test sounds to your audio system via AirPlay and Bluetooth.  Tap the AirPlay symbol at the bottom of the screen to see a list of valid connections.

HouseCurve will default to using the built in microphone of your iPhone/iPad.  HouseCurve will automatically use an external microphone if one is connected to your iPhone/iPad.

At the bottom of the screen, HouseCurve displays where it is sending audio and what microphone is in use.

### HouseCurve shows me how my audio system sounds, but how do I tune it?
It depends on your audio system and where it is located.  It is best to make small adjustments and use HouseCurve to see the effect.  Over time, you’ll learn what works for your system.

The most direct way to tune your system is to adjust the equalizer or bass/treble knobs.  If you have a subwoofer, then you can also adjust the volume, phase, polarity and crossover frequency.

The room also has a significant impact on what you hear.  Move your speakers closer to a wall to increase low frequencies.  Drapes and furniture can reduce high frequencies because they change how sound reflects in the room (absorbing or diffusing the sound).

### Why isn’t a flat reference curve included?
When listening to music, most listeners prefer in-room frequency responses with roughly a 3 db/decade downward slope.  A flat response tends to sound overly “bright”.  However, HouseCurve can import custom curves, so try it for yourself: [Flat Reference Curve](/examples/flat.txt).

Here are some resources for understanding house curves:
* [Relevant loudspeaker tests, in studios, in Hi-Fi dealers' demo rooms, in the home etc](https://www.bksv.com/media/doc/17-197.pdf)
* [The Measurement and Calibration of Sound Reproducing Systems](http://www.aes.org/e-lib/browse.cfm?elib=17839)
* [The Subjective and Objective Evaluation of Room Correction Products](https://seanolive.blogspot.com/2009/11/subjective-and-objective-evaluation-of.html)
* [House Curve: What it is, why you need it, how to do it](https://www.hometheatershack.com/forums/rew-forum/96-house-curve-what-why-you-need-how-do.html)

### When to use log sine versus pink noise?

The log sine sweep will generally do a better job of capturing the sound of a typical household room.  Pink noise stimulus is what HouseCurve originally used by default.  HouseCurve is less sensitive to interference when using pink noise, if measurements are failing due to "interference detected", try using pink noise.

### I keep getting "interference detected", what's wrong?

In a noisy environment (ex: people talking louder than test signal), HouseCurve will reject measurements.  If this is the case, reduce the noise or increase the volume.

This can also happen when one speaker is playing much louder than the rest of the audio system (ex: subwoofer that's too loud).  Try changing the stimulus to pink noise by going to **Setup**.  Pink noise measurements are more likely to succeed and can be used to diagnose if this is the issue (look for large swings in measurement).

### I have a question and/or feedback, where do I send it?
Suggestions and questions are welcome, please send to [HouseCurve support](mailto:support@housecurve.com).

