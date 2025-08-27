# Shoreline Wave Tracking and Wave Period Estimation

This repository contains a **Jupyter notebook** that provides an end-to-end pipeline for tracking shoreline waves and estimating the **wave period (Tp)** from video footage. The pipeline utilizes **computer vision** and **signal processing** techniques to extract features from video frames and compute wave periods using various estimation methods.

## Features

### Video Processing

* Loads video files and processes frames for analysis.
* Optional **video stabilization** using **ECC-based methods** for improved tracking.

### Region of Interest (ROI) Detection

* **Automatic detection** of the water region in each frame for wave analysis.
* Supports both **automatic** and **manual** ROI selection.

### Optical Flow Calculation

* Computes **optical flow** between consecutive frames using the **Farnebäck method** to estimate motion.
* Optionally smooths the flow to improve accuracy in wave tracking.

### Wave Period Estimation

The notebook extracts wave period (`Tp`) using multiple signal processing techniques:

1. **Zero-crossing method** (`Tz`).
2. **Power Spectral Density** (`PSD`).
3. **Autocorrelation Function** (`ACF`).
4. **Fused Tp** from the above methods.
5. Performs **rolling window analysis** to compute **time-varying wave periods**.

### Visualization

* Overlays **estimated wave periods** on the video.
* Provides an option to **save and download** the processed video and results.
* Plots the **estimated wave periods** over time.

### Output

* Generates a **CSV file** containing the estimated wave periods (`Tp`) and their **confidence levels**.
* Saves the processed video with **wave period annotations** on each frame.

## Requirements

This project requires the following Python libraries:

* `cv2` (OpenCV)
* `torch` (PyTorch)
* `numpy`
* `matplotlib`
* `scipy`
* `transformers`
* `tqdm`
* `pandas`

You can install all dependencies by running the following command:

```bash
pip install -r requirements.txt
```

Alternatively, you can install each package individually using `pip`:

```bash
pip install opencv-python torch numpy matplotlib scipy transformers tqdm pandas
```

## How to Use

### 1. Upload Video

* Upload a video file containing shoreline footage.
* The notebook will automatically detect frames from the video.

### 2. Region of Interest (ROI) Selection

* The ROI will be automatically detected, or you can manually select the region containing the water.

### 3. Wave Period Estimation

* The notebook will extract wave periods using multiple signal processing methods.
* A **CSV file** with the results will be generated.

### 4. Visualization

* The results will be overlaid on the video.
* The processed video can be saved and downloaded along with the **CSV file** for further analysis.

## Example Output

After running the pipeline, you will get:

### 1. Rolling Wave Period Results (CSV File)

This file contains the following columns:

* `Timestamp`
* `Tp_zero` (Zero-crossing period)
* `Tp_psd` (PSD period)
* `Tp_acf` (ACF period)
* `Tp_fused` (Fused period)
* `Confidence`

### 2. Processed Video

A video with **wave period annotations** on each frame.

## Use Cases

This notebook is useful for:

* **Oceanography & Coastal Research**: Estimating wave characteristics in shoreline and coastal environments.
* **Video Analysis**: Applying computer vision techniques to estimate wave periods.
* **Environmental Monitoring**: Tracking wave behavior in natural settings.

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

