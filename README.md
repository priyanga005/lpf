% Frequency Analysis Using FFT in MATLAB
clc;
clear;

% Parameters
fs = 1000;  % Sampling frequency in Hz
t = 0:1/fs:1-1/fs;  % Time vector
signal = 3*sin(2*pi*50*t) + 2*sin(2*pi*120*t);  % Example signal

% Perform FFT
N = length(signal);  % Number of samples
fft_result = fft(signal);  % Compute FFT
fft_magnitude = abs(fft_result(1:N/2+1)) * (2 / N);  % Magnitude spectrum (normalized)
frequencies = (0:N/2) * (fs / N);  % Frequency bins for positive spectrum

% Plot the results
figure;
plot(frequencies, fft_magnitude, 'b', 'LineWidth', 1.5);
title('Frequency Analysis using FFT');
xlabel('Frequency (Hz)');
ylabel('Magnitude');
grid on;
