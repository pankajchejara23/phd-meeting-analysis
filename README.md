# Phd meeting data analysis
This repository contains python codes used to analyse PhD meeting data (audio+video) to understand the group dynamics and explore types of potential features for understanding group exchange.

# Data collection
The data used in this analysis are collected using [CoTrack](https://www.cotrack.website/) tool from an online setting. There were four participants in the meeting and their audio and video data were recorded using the tool.

# Data preprocessing
First of all, the individual video recordings were synchronized using the timestamp information. Once synchronized, the audio was extracted for each participant.

## Voice activity detection
The extracted audio used with Voice Activity Detection (VAD) method to identify voice activity. To check the accuracy of VAD, 20 minutes audio of a participant was annotated and used to compute the accuracy of VAD. The accuracy was found 94% using pyannote tool.

VAD results
![vad](https://user-images.githubusercontent.com/21138354/147817589-a00b95fe-8b6c-41e5-a149-ca2374da9e7c.png)

Ground truth
![gd](https://user-images.githubusercontent.com/21138354/147817625-79b777a8-33b9-490a-8126-a0def490b8fa.png)

Performance of VAD
```
Detection accuracy: 0.9443070805453685
Detection error rate: 0.25243702478729363
Detection cost function: 0.061424020959540235
```


VAD features are used to compute the speaking time and turn-taking behavior of each participant. These features then used to generate a 'who is talking after whom' network illustrating the group dynamics.
Example is given below
![net](https://user-images.githubusercontent.com/21138354/147817684-f1e7716a-d403-4934-abd6-9a89cb474eab.png)
