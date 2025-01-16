# ✨ PhD Meeting Data Analysis ✨

This repository contains Python code for analyzing PhD meeting data (audio and video) to better understand group dynamics and explore potential features related to group exchanges. The project involves data preprocessing, voice activity detection, and network analysis to visualize interactions among participants.

## 📊 Data Collection

The data used in this analysis were collected using the [CoTrack](https://www.cotrack.website/) tool in an online setting. The meeting included four participants, and their audio and video data were recorded using the tool.

## ⚙️ Data Preprocessing

### ⌚ Synchronization
Individual video recordings were synchronized using timestamp information to ensure accurate alignment.

### 🎧 Audio Extraction
Once synchronized, audio data were extracted for each participant.

## 🎶 Voice Activity Detection (VAD)

The extracted audio data were processed using a Voice Activity Detection (VAD) method to identify when participants were speaking. The accuracy of the VAD method was verified by annotating 20 minutes of audio data from one participant. Using the [pyannote.audio](https://github.com/pyannote/pyannote-audio) tool, the accuracy metrics were computed as follows:

```
Detection accuracy: 0.944
Detection error rate: 0.252
Detection cost function: 0.061
```

### ★ Results
- **VAD Output**
  ![vad](https://user-images.githubusercontent.com/21138354/147817589-a00b95fe-8b6c-41e5-a149-ca2374da9e7c.png)

- **Ground Truth**
  ![gd](https://user-images.githubusercontent.com/21138354/147817625-79b777a8-33b9-490a-8126-a0def490b8fa.png)

### 🔄 Features Extracted
1. Speaking time for each participant.
2. Turn-taking behavior.

These features were used to generate a "who is talking after whom" network, illustrating the group dynamics.

#### 🔍 Example Network Visualization
![net](https://user-images.githubusercontent.com/21138354/147817684-f1e7716a-d403-4934-abd6-9a89cb474eab.png)

## 🔢 Notebook
The main analysis is available in the Jupyter Notebook: [PhD Meeting Analysis](https://github.com/pankajchejara23/phd-meeting-analysis/blob/master/PhD%20meeting%20analysis.ipynb)

The notebook contains step-by-step code for:
- Data preprocessing
- Voice activity detection
- Feature computation
- Network visualization

## 🛠️ Tools and Libraries
- [CoTrack](https://www.cotrack.website/): For data collection
- [pyannote.audio](https://github.com/pyannote/pyannote-audio): For voice activity detection
- Python libraries: `numpy`, `pandas`, `networkx`, `matplotlib`, etc.


## 📄 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
