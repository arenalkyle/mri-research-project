# Fourier Transform's Role in Magnetic Resonance

This repository contains research and presentation materials exploring how the **Fourier Transform (FT)** serves as the mathematical foundation for converting raw magnetic resonance signals into anatomical images.

## Project Overview
Magnetic Resonance Imaging (MRI) is a non-invasive process that maps hydrogen nuclei signals to recreate 3D images. The core challenge in MR is localizing these signals, which is achieved through spatial encoding using magnetic field gradients. This research analyzes how the FT and Fast Fourier Transform (FFT) are utilized to bridge the gap between raw data (K-space) and the final reconstructed image.


## Key Concepts

### 1. Signal Generation & Spatial Encoding
* **Net Magnetization (M):** MRI manipulates the "spin" of protons in the body using a strong external magnetic field ($B_{0}$) to create a measurable signal.
* **Larmor Equation:** The precession frequency of these protons is directly proportional to the magnetic field strength: $\omega_{0}=\gamma B_{0}$.
* **Gradients:** Three magnetic gradients ($G_{x},  G_{y},  G_{z}$) are applied in sequence to provide spatial localization through Slice Selection, Phase Encoding (PE), and Frequency Encoding (FE).

### 2. K-Space: The Data Bridge
The raw signal, known as **Free Induction Decay (FID)**, is organized into a 2D data matrix called **K-space**.
* **Center of K-space:** Contains low-frequency data responsible for image contrast and general shape.
* **Edges of K-space:** Contains high-frequency data that defines sharp edges and fine details.


### 3. Image Reconstruction (FFT)
To transform K-space data back into a viewable image, an **Inverse Fourier Transform (IFT)** is required.
* **Efficiency:** In clinical practice, the **Fast Fourier Transform (FFT)** is used. It employs a "divide and conquer" algorithm, reducing computational complexity from $\theta(N^2)$ to $\theta(N\log_2 N)$.
* **Performance:** For a standard $256 \times 256$ matrix, FFT is approximately 32 times faster than a standard Discrete Fourier Transform (DFT).

## Image Quality & Artifacts
The parameters used to sample K-space directly impact the final image:
* **Resolution:** Determined by the total width of the K-space matrix.
* **Field of View (FOV):** Inversely proportional to the sampling interval ($\Delta k$).
* **Aliasing:** Occurs when under-sampling violates the Nyquist criterion, causing the image to "wrap around" or appear warped.

## Presentation
You can watch the full presentation of this research here: [Fourier Transform in MRI - Video Presentation](https://youtu.be/MiX36rj9bow)

---

**Author:** Kyle Arenal 
