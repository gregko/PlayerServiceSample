# Android PlayerServiceSample
Trivial Android player service that handles media buttons, based on the Gist by ianhanniballlake:
https://gist.github.com/ianhanniballake/15dce0b233b4f4b23ef8. It shows only a LocCat output like

KEYCODE_MEDIA_PLAY

when media button Play is pressed on a headset. It works under Android versions
5.xx up to 7.xx, but fails under Android 8 "Oreo". Tested on the final release of Oreo, build
number OPR6.170623.013, Nexus 6P. Could someone tell me what's wrong and how to fix media
button handling on Android 8 Oreo?

**Sept. 1, 2017 - Solved**

Android 8 Oreo sends media button events to the app that last played sound, and does not care
about MediaSession setActive() and other calls... Trouble is that is must be MediaPlayer sound,
they ignore speech generated with TextToSpeech API. A bug in my opinion, will follow to submit
it to Android issue tracker, but at least have a work-around now - play a very short and silent
WAV file (from resources or assets) when media buttons focus is needed. Such a stupidity...
