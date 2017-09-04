# Android PlayerServiceSample
Trivial Android player service that handles media buttons, that demonstrates a problem with
 media button handling under Android 8 "Oreo". It is based on the Gist by ianhanniballlake:
https://gist.github.com/ianhanniballake/15dce0b233b4f4b23ef8. It shows only text output when
media buttons are pressed on any headset.

It works fine under Android versions 5.xx up to 7.xx, but fails under Android 8 "Oreo", even
after playing a TTS sample from the button. It should bring media button focus to this app
(there are people who listen to entire audio-books or long lists of articles with TTS, through
Bluetooth and wired headsets), but it fails. The only known work-around is to use MediaPlayer
to play a very short silent WAV file, only this brings media button focus to a TTS only app...

Tested on the final release of Oreo, build number OPR6.170623.013, Nexus 6P. 
