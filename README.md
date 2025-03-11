# AutoMusic
Where I try to teach a computer to know about electronic music. This is very much a work-in-progress.

(If it seems like I don't know exactly what I'm doing, you are entirely correct. Please help!)

Mostly a series of Python sketches in TensorFlow and Keras trained via with [PyRekordBox](https://github.com/dylanljones/pyrekordbox) which creates a robust pre-labeled dataset of music with labels from RekordBox's phrase analysis system. 

My end goal is to have "phrases" in electronic music mostly properly identified in real-time so I can make lighting (like in [WLED MoonModules](https://github.com/MoonModules/WLED) react to the musical "movement" and not just the waveforms. 

Mostly tested and trained for what I play when I DJ (House-related, NuDisco, house remixes of older songs, etc in a 120-130ish BPM range) - which is what RekordBox generally calls the "high" mood, and 10 extended labels of 'high_intro_1', 'high_intro_2', 'high_chorus_1', 'high_chorus_2', 'high_down', 'high_up_1', 'high_up_2', 'high_up_3', 'high_outro_1', and 'high_outro_2'. There are also "mid" and "low" analysis formats, but I have found not much of what I play is in the "mid" cateegory, and nothing is in the "low" category except literally low energy music like slow jams. A version of the model trained on all these tags was rather poor performing as there wasn't much training data in those labels, so I stuck with what I generally play when I DJ.

![image](https://github.com/user-attachments/assets/5736d09b-f33d-49bc-b77c-aee8d6a1eb6f)

(This image is NOT a progressive training on the same model - model was improved and completely retrained and errors fixed a few times.)

The system captures a log of the files as it suimulates playback, and saves some of the mislabeled segments for later retraining. A bad result later is actually a good training result, as the system will learn to generalize better - I think.

The current model seems to generalize pretty well - I have tested a few songs at every possible 3-second sample in the song (across 3000 offsets) and the analysis is pretty good at at recognizing a label even when alignment varies.

![image](https://github.com/troyhacks/AutoMusic/assets/5659019/443d6209-eb2f-4bc0-8a83-5c7271d5d688)

Training testing continues, and I have some ideas for scanning a file more quickly than taking 3000*seconds_of_length/3 samples to figure out how well it's generalizing - because it seems best to train on the "worst" offsets rather than random offsets. With the current results, I'm watching more for an overall improvement in the correct % scores rather than a high score - unless every file suddenly jumps together.

Currently I am also confirming the model using a sample of files mostly "unseen" during training - and it does seem to work well even on tracks not in the training data. 

I will repeat that I'm basically making very vaguely educated guesses at this point - but I wanted to release something with the hope that prehaps more eyeballs will make it better.

A huge thanks to [Dylan Jones](https://github.com/dylanljones) for [PyRekordBox](https://github.com/dylanljones/pyrekordbox) upon which all the labeling is derived. 
