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
pandas
scipy

To install the dependencies, you can run this command:
pip install matplotlib numpy seaborn nbimporter pandas scipy

Step-by-Step usage:

In file code_.ipynb: 

1. You use the function read_csv_multi(filename) to load ECG data.
2. Each file is assumed to have 12 channels of ECG signals, each line containing one time point per channel.
3. You define the function savgol_filter(signal, window_size, poly_order) to smooth noisy ECG signals.
4. The filter computes polynomial coefficients using matrix operations (multiplication, transpose, inverse).
5. You apply it to each channel and visualize both the original and filtered signals using matplotlib.

In file snr.ipynb:

1. You define compute_snr(original, denoised) which compares the filtered signal to the original one and calculates SNR in decibels
2. You apply this for combinations of window_size and poly_order over a subset of ECG files and save average SNRs.
3. You use nested loops over combinations of window sizes and polynomial orders (where poly_order < window_size).
4. For each combination, you compute average SNR over 3 channels and 2000 points per file
5. Best-performing configuration is selected
6. You visualize the SNR values as a heatmap using seaborn.

In file RMSE.ipynb:

1. Similar to SNR, you define compute_rmse(original, filtered)
2. You apply this to each (window_size, poly_order) combination and save average RMSEs.
3. Again, the best configuration is selected based on lowest RMSE (but in your code, it mistakenly chooses the max — should be min).
4. You store the RMSE values in a 2D array and display them with a custom color heatmap.

In benchmarks.ipynb:
