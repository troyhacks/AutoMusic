# AutoMusic
Where I try to teach a computer to know about electronic music.

Mostly a series of Python sketches in TensorFlow and Keras with [PyRekordBox](https://github.com/dylanljones/pyrekordbox) helping create a robust pre-tagged feed of music with labels from their phrase analysis system. 

My end goal is to have "phrases" in electronic music mostly properly identified in real-time so I can make lighting (like in [WLED MoonModules](https://github.com/MoonModules/WLED) react to the music and not just thhe waveforms. 

Mostly tested and trained for what I play when I DJ (House-related, NuDisco, house remixes of older songs, etc in a 120-130ish BPM range) - which is what RekordBox generally calls the "high" mood, and 5 tags of 'high_intro', 'high_chorus', 'high_down', 'high_up', and ,'high_outro'.

![image](https://github.com/troyhacks/AutoMusic/assets/5659019/1a1a17bc-b304-4f3a-9c94-f00cf1474536)

The system captures a log of the files as it suimulates playback, and saves some of the mislabeled segments for later retraining.

A huge thanks to [Dylan Jones](https://github.com/dylanljones) for [PyRekordBox](https://github.com/dylanljones/pyrekordbox) upon which all the labeling is derived. 
