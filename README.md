# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

_program_:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

# Given values
Am = 2.24
Fm = 12
Ac = 5.6
Fc = 24
Fs = 240

t = np.arange(0, 2/Fm, 1/Fs)

# Message signal
em = Am * np.sin(2 * np.pi * Fm * t)

# Carrier signal
ec = Ac * np.sin(2 * np.pi * Fc * t)

# AM Modulated signal
eam = (Ac + Am * np.sin(2 * np.pi * Fm * t)) * np.sin(2 * np.pi * Fc * t)

# Demodulated signal using Hilbert transform
demodulated_signal = np.abs(hilbert(eam)) - Ac

# Plotting
plt.figure(figsize=(10, 10))

plt.subplot(4, 1, 1)
plt.plot(t, em)
plt.title("Message Signal")
plt.grid(True)

plt.subplot(4, 1, 2)
plt.plot(t, ec)
plt.title("Carrier Signal")
plt.grid(True)

plt.subplot(4, 1, 3)
plt.plot(t, eam)
plt.title("AM Modulated Signal")
plt.grid(True)

plt.subplot(4, 1, 4)
plt.plot(t, demodulated_signal)
plt.title("Demodulated Signal")
plt.grid(True)

plt.tight_layout()
plt.show()
```
_Tabulation_:

![WhatsApp Image 2025-11-24 at 18 27 09_14da9991](https://github.com/user-attachments/assets/ad741429-0a0f-4bb7-b1ec-99ad591710df)

![WhatsApp Image 2025-11-24 at 18 27 10_0ff94320](https://github.com/user-attachments/assets/d8bbc2a4-4ec1-40b5-a5a0-3f49ed371659)

 __Output__:

![WhatsApp Image 2025-11-15 at 13 32 31_2ab29992](https://github.com/user-attachments/assets/2819076b-251e-4339-aadc-8232393162ed)

 __Result__:

Thus the AM demodulation and modulation is verified using python successfully.
