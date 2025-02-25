# ECG Signal Processing & Median Filter

## Overview

This project focuses on processing ECG signals using analog  filtering techniques. The system includes amplification, phase shifting, and multiple filtering stages, including a median filter, notch filter, high-pass filter, and low-pass filter. These components work together to enhance signal clarity and remove noise for accurate ECG analysis. For more details about the project, checkout this [report](https://docs.google.com/document/d/1m3WGtXcJivpxO5Qh31EQCQH-g_JgQbG-oU1WNG2gprk/edit?tab=t.0)

## Problem Statement

ECG signals are highly susceptible to noise from power lines, muscle activity, and baseline wander. To ensure accurate interpretation, it is crucial to remove these interferences while preserving important signal features.

## Solution

1. The signal processing pipeline involves the following steps:

2. Simulating the ECG signal and adding noise:

3. ECG data is generated and converted into a .txt file using a Python script.

4. Noise (White Gaussian Noise) is introduced in LTSpice using a behavioral voltage component.

5. Amplification and Phase Shifting:

6. The raw ECG signals are amplified using non-inverting op-amp circuits (gain ≈ 1000).

7. All-pass filters are used to phase-shift the signals to generate multiple delayed versions for median filtering.

## Filtering and Noise Reduction:

1. Median Filter: This custom-built analog filter takes in five phase-shifted inputs and outputs the median value, effectively removing impulsive noise while preserving waveform integrity. Either we can use a median filter with 5 to 7 inputs, and it gives the same results as using low-pass, notch, and high-pass filters combined.

2. Notch Filter: Eliminates powerline interference (60 Hz and 160 Hz) using a combination of high-pass and low-pass filters connected through a summer circuit.

3. High-Pass Filter: Removes baseline wander and low-frequency noise with a cutoff at 0.2 Hz.

4. Low-Pass Filter: Attenuates high-frequency noise, limiting the bandwidth to 25 Hz.

## Features

1. Custom-designed median filter for ECG signals.

2. High-fidelity filtering with Butterworth characteristics.

3. Powerline noise suppression using notch filtering.

4. Baseline correction and high-frequency noise reduction.

5. Phase-shifted inputs to ensure accurate median computation.

## Conclusion

This ECG signal processing system provides a robust solution for filtering and noise removal. By incorporating an analog median filter, the design ensures minimal signal distortion while effectively removing impulsive noise. Yet modifications are to be made in the design, to make it a lot simpler than the current design!
