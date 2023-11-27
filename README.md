# AutoMusic
Where I try to teach a computer to know about electronic music. This is very much a work-in-progress.

(If it seems like I don't know exactly what I'm doing, you are entirely correct. Please help!)

Mostly a series of Python sketches in TensorFlow and Keras trained via with [PyRekordBox](https://github.com/dylanljones/pyrekordbox) which creates a robust pre-labeled dataset of music with labels from RekordBox's phrase analysis system. 

My end goal is to have "phrases" in electronic music mostly properly identified in real-time so I can make lighting (like in [WLED MoonModules](https://github.com/MoonModules/WLED) react to the musical "movement" and not just the waveforms. 

Mostly tested and trained for what I play when I DJ (House-related, NuDisco, house remixes of older songs, etc in a 120-130ish BPM range) - which is what RekordBox generally calls the "high" mood, and 5 tags of 'high_intro', 'high_chorus', 'high_down', 'high_up', and ,'high_outro'.

![image](https://github.com/troyhacks/AutoMusic/assets/5659019/87fee816-6d96-43a7-b4e5-867f64416b3d)

The system captures a log of the files as it suimulates playback, and saves some of the mislabeled segments for later retraining.

The current model seems to generalize pretty well - I have tested a few songs at every possible 3-second sample in the song (across 3000 offsets) and the analysis is pretty good at at recognizing a label even when alignment varies.

![image](https://github.com/troyhacks/AutoMusic/assets/5659019/443d6209-eb2f-4bc0-8a83-5c7271d5d688)

A huge thanks to [Dylan Jones](https://github.com/dylanljones) for [PyRekordBox](https://github.com/dylanljones/pyrekordbox) upon which all the labeling is derived. 
