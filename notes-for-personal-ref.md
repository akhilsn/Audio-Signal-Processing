## NOTES:

#### Short Time Fourier Transform (STFT)
- enables us to extract Spectrograms (which happen to be a very important feature that can be fed to a deep learning network)

Why STFT?
To understand 'why stft', we need to first understand the shortcoming of the magnitude spectrum that is obtained by a DFT over an audio signal. 
The magnitude spectrum obtained is basically a picture of all the frequency components averaged across the whole duration of the audio signal. This creates a problem, bcoz
We know what all frequency components are present, but we do not know when are they present across the signal.

Since the audio data is all about dynamic evolution of frequency components over time, the 'when' information is crucial -> STFT lets us save this crucial information by considering small segments of the signal (instead of whole duration of signal) and applying FFT locally.

The segmenting of the signal could be done by making use of Windowing function to signal.

![image](https://user-images.githubusercontent.com/60335981/125161790-f6b56780-e1a1-11eb-8d8e-42e60d89f838.png)


### Recipe to extract Mel-Spectrograms:

1. Extract STFT
2. Convert Amplitude to DBs
3. Convert Frequencies to Mel-scale.

### Convert Frequencies to Mel-Scale:

1. Choose number of Mel-Bands
2. Construct Mel-Filter Banks
3. Apply Mel-Filter to Spectrograms
