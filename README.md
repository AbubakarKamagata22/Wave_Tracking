**Shoreline Wave Tracking and Wave Period Estimation**

This repository contains a Jupyter notebook that provides an end-to-end pipeline for tracking shoreline waves and estimating the wave period (Tp) from video footage. The pipeline utilizes computer vision and signal processing techniques to extract features from video frames and compute wave periods using various signal processing methods.
Features

_Video Processing:_

Loads video files and processes frames for analysis.
Optional video stabilization using ECC-based methods for improved tracking.

_Region of Interest (ROI) Detection:_

Automatically detects and selects the water region in each frame for wave analysis.
Supports both automatic and manual ROI selection.

_Optical Flow Calculation:_

Computes optical flow between consecutive frames using the Farnebäck method to estimate motion.
Optionally smooths the flow to improve accuracy in wave tracking.

_Wave Period Estimation:_

1. Extracts wave period (Tp) using multiple techniques:
2. Zero-crossing method (Tz).
3. Power Spectral Density (PSD).
4. Autocorrelation Function (ACF).
5. Fused Tp from the above methods.
6. Performs rolling window analysis to compute time-varying wave periods.

_Visualization:_

Overlays estimated wave periods on the video, with an option to save and download the processed video and results.
Plots the estimated wave periods over time.

_Output:_

Generates a CSV file with the estimated wave periods and their confidence levels.
Saves the processed video with wave period annotations.

_Requirements_

This project requires the following Python libraries:

a. cv2 (OpenCV)
b. torch (PyTorch)
c. numpy
d. matplotlib
e. scipy
f. transformers
g. tqdm
h. pandas

_Install these dependencies using:_

pip install -r requirements.txt
Alternatively, you can install each package individually via pip:

pip install opencv-python torch numpy matplotlib scipy transformers tqdm pandas

**How to Use**

_Upload Video:_

Upload a video file containing shoreline footage. The notebook will automatically detect frames from the video.
_Region of Interest (ROI) Selection:_
The ROI will be automatically detected, or you can manually select the region that contains the water.

_Wave Period Estimation:_
The notebook will extract wave periods using multiple signal processing methods and generate a CSV file with the results.

_Visualization:_
The results will be overlaid on the video, and the processed video will be saved.
You can download the video and CSV file for further analysis.

**Example Output**

_After running the pipeline, you will get:_

_Rolling Wave Period Results: A CSV file containing:_

_Timestamp_
1. Tp_zero (Zero-crossing period)
2. Tp_psd (PSD period)
3. Tp_acf (ACF period)
4. Tp_fused (Fused period)
5. Confidence

**Processed Video: A video with wave period annotations on each frame.**

**Use Cases**

_This notebook is useful for:_

Oceanography & Coastal Research: Estimating wave characteristics in shoreline and coastal environments.

Video Analysis: Applying computer vision techniques to estimate wave periods.

Environmental Monitoring: Tracking wave behavior in natural settings.
