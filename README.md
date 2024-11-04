# Real-Time Canny Edge Detection with OV7670 Video Streaming

This project demonstrates a real-time implementation of the Canny edge detection algorithm using the OV7670 camera module on the Nexys-A7 FPGA. Developed as part of a summer internship with teammates Gaurav and Naitik, and under the guidance of Dr. Ankur Changla, the project aims to explore hardware-based computer vision applications. We also explored the potential for ASIC implementation for future projects.

## Table of Contents
- [Project Overview](#project-overview)
- [The Canny Edge Detection Algorithm](#the-canny-edge-detection-algorithm)
- [Implementation Details](#implementation-details)
- [Hardware Setup](#hardware-setup)
- [Demo Video](#demo-video)
- [Usage](#usage)
- [Contributors](#contributors)
- [License](#license)

## Project Overview

The primary objective of this project was to implement the Canny edge detection algorithm on an FPGA to achieve real-time edge detection from a live video stream. The OV7670 camera captures the video stream, which is then processed on the FPGA and displayed on a VGA monitor. The implementation demonstrates how hardware acceleration can efficiently handle computational tasks like edge detection, paving the way for potential ASIC designs.

## The Canny Edge Detection Algorithm

The Canny edge detection algorithm is a multi-step process:
1. **Noise Reduction**: A Gaussian filter smooths the image, reducing noise and false edges.
2. **Gradient Calculation**: The Sobel operator calculates the image gradient, identifying areas with high intensity changes.
3. **Non-Maximum Suppression**: Suppresses non-maximum gradient values to refine edges.
4. **Double Thresholding**: Classifies pixels as strong or weak edges based on high and low thresholds.
5. **Edge Tracking by Hysteresis**: Retains weak edges only if they connect to strong edges, ensuring edge continuity.

## Implementation Details

### Hardware Components
- **FPGA Board**: Nexys-A7 FPGA was chosen for its flexibility and resource availability.
- **Camera Module**: OV7670 camera for capturing live video input.
- **Display**: VGA port output for displaying the processed edge-detected video in real time.

### FPGA Design
- **Image Input**: Real-time data from the OV7670 camera is fed to the FPGA.
- **Gaussian Filter**: A 5x5 Gaussian kernel is implemented for noise reduction using parallel processing.
- **Sobel Operator**: A 3x3 convolution kernel calculates gradients in the x and y directions, using parallelization for real-time performance.
- **Non-Maximum Suppression and Thresholding**: Implemented in hardware using decision logic to optimize memory and resource usage.
- **VGA Output**: The processed data is sent to a VGA display for real-time visualization of detected edges.

## Hardware Setup

1. Connect the OV7670 camera module to the Nexys-A7 FPGA.
2. Connect a VGA-compatible monitor to the VGA port of the FPGA.
3. Power up the FPGA and load the bitstream to initiate the real-time edge detection process.

## Demo Video

You can see the working architecture and output demonstration in the video below:
- [Demo Video Link](#) *(Replace with the actual link to the video)*

## Usage

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/real-time-canny-edge-detection-fpga.git
