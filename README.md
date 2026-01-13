# Audio Sound Classification using ANN

This project focuses on **audio sound classification** using an **Artificial Neural Network (ANN)**.  
The goal is to convert real-world sounds into numerical features and learn patterns that distinguish between **10 different sound classes**, such as dog barking, car horn, siren, and similar environmental sounds.

The project follows a standard and practical machine learning workflow for audio data:  
**audio signal → feature extraction → numerical representation → neural network training**.

---

## Sound Classes

The dataset contains audio samples belonging to the following 10 classes:

1. Dog Bark  
2. Car Horn  
3. Siren  
4. Gun Shot  
5. Engine Idling  
6. Street Music  
7. Air Conditioner  
8. Children Playing  
9. Jackhammer  
10. Drilling  

Each class represents a distinct type of environmental sound.

---

## How the Model Works

Audio files are not directly suitable for machine learning models because they are raw waveforms.  
To make them usable, the audio is first **processed and converted into numerical features** that capture important sound characteristics.

The general pipeline is:

1. Load audio files  
2. Extract meaningful features from the sound signal  
3. Convert those features into numerical arrays  
4. Feed the numerical data into an Artificial Neural Network  

---

## Feature Extraction using MFCC

The core feature used in this project is **MFCC (Mel-Frequency Cepstral Coefficients)**.

### What is MFCC?

MFCCs are a compact numerical representation of an audio signal that capture how humans perceive sound.  
Instead of working directly with raw waveforms, MFCCs describe **frequency patterns** in a way that is more meaningful for learning algorithms.

In simple terms:
- Humans do not hear frequencies linearly
- MFCCs transform sound into a scale that matches human hearing
- This helps the model focus on important audio characteristics

---

### How MFCCs are Generated

For each audio file, the following steps are applied:

1. **Load the audio signal**  
   The audio file is loaded using libraries like `librosa`, producing a waveform and sample rate.

2. **Convert to frequency domain**  
   The signal is split into short frames, and a Fourier Transform is applied to analyze frequencies.

3. **Apply Mel scale**  
   Frequencies are mapped to the Mel scale, which emphasizes frequencies humans hear more clearly.

4. **Log transformation**  
   Loudness differences are compressed using a logarithmic scale.

5. **Cepstral coefficients extraction**  
   The final MFCC values are computed, resulting in a fixed-size numerical feature vector.

The output of this process is a **matrix of numbers**, where each value represents an important characteristic of the sound.

---

### Why MFCCs are Used

MFCCs are widely used in:
- Speech recognition
- Environmental sound classification
- Audio event detection

They reduce raw audio data into a **compact and informative numerical form**, making them well-suited for neural networks.

---

## Neural Network (ANN)

The extracted MFCC features are flattened and passed into an **Artificial Neural Network**.  
The ANN learns patterns in the numerical data that correspond to different sound categories.

- Input layer receives MFCC-based feature vectors  
- Hidden layers learn relationships between features  
- Output layer represents the sound classes  

This structure allows the model to learn complex patterns present in audio signals.

---

## Libraries Used

The project relies on the following libraries:

- `librosa` – audio loading and feature extraction  
- `soundata` – audio dataset handling  
- `numpy` – numerical operations  
- `matplotlib` – waveform and feature visualization  
- `scikit-learn` – preprocessing utilities  
- Deep learning framework (as specified in `requirements.txt`)  

---

## Project Folder Structure

audio-sound-classification/
│
├── src/
│ ├── model.ipynb
│
├── requirements.txt # Python dependencies
├── README.md
└── .gitignore


## Dataset

The dataset used in this project can be downloaded from the following link:

Dataset Link:  https://urbansounddataset.weebly.com/urbansound8k.html

OR

You can download it from soundata library(guidance is given in the .ipynb notebook).

## Setup Instructions

Clone the repository:
git clone https://github.com/huzayfaSiddique/audio-sound-classification.git

Install required libraries:
pip install -r requirements.txt

##Summary
This project demonstrates a complete and practical approach to audio sound classification, starting from raw audio signals and ending with numerical feature learning using an Artificial Neural Network.
The use of MFCCs allows the model to work with meaningful audio features rather than raw waveforms.