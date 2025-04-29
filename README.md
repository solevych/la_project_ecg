ECG Signal Denoising using Savitzky-Golay Filter

Project overview:

This repository focuses on denoising ECG signals using the Savitzky-Golay filter, and evaluating its effectiveness using SNR and RMSE across different polynomial orders and window sizes. The implementation is done from scratch, without relying on external filtering libraries, to gain insight into matrix-based signal smoothing.

We use a clinical-grade ECG dataset for testing, provided by Chapman University and Shaoxing People's Hospital, containing 12-lead ECG signals from 10,646 patients, sampled at 500 Hz.

Dataset Description:
This ECG database was created to support the development and evaluation of automated algorithms for cardiovascular diagnostics. Key features:
- 12-lead ECG signals per patient
- 500 Hz sampling rate
- Labeled by professionals for 11 common rhythms and 67 conditions
Data format: .csv files with 12 comma-separated values per line (each representing a lead/channel)


Requirements:

This project uses the following Python libraries that must be installed:
matplotlib
numpy
seaborn
nbimporter

To install the dependencies, you can run this command:
pip install matplotlib numpy seaborn nbimporter



