# Product Recognition on Store Shelves

## Introduction
This project focuses on detecting objects in supermarket scenarios. The core objective is to identify and recognize cereal boxes from various brands on store shelves, using computer vision techniques.

## Methodology
The project is divided into two main tasks:

### Task A: Single Product Identification
- **Objective**: Identify a single instance of each product in a picture.
- **Approach**: Utilizes Scale-invariant feature transform (SIFT) to identify key points and descriptors in product images (Models) and images of supermarket shelves (Scenes). Feature matching is performed using a KNN FLANN-based matcher, followed by RANSAC to create a homography. Additional validation is done by checking the outline's shape and colour matching to ensure accurate product identification.

### Task B: Multiple Product Instances Identification
- **Objective**: Extend detection capabilities to identify one or more instances of various products within a given scene.
- **Approach**: Combines local invariant features with the Generalized Hough Transform (GHT) to enhance accuracy. This complex approach starts similarly to Task A but incorporates GHT for better localization of product instances, including adjustments for overlapping detections.

## Results
The system demonstrated a high degree of accuracy in detecting cereal boxes in supermarket shelf images for both tasks. Adjustments to parameters like colour threshold and a minimum number of matches can affect detection sensitivity, highlighting the system's adaptability to different scenarios.

## Code Usage

### Setup
Ensure you have Python and necessary libraries (OpenCV, numpy, matplotlib) installed. Clone this repository to your local machine.

- Open `stepA.ipynb` to execute Task A for single product detection.
- Open `stepB.ipynb` to run Task B to detect multiple product instances.

### Input Data
The project uses two sets of images:
- Models: Images of individual cereal box products.
- Scenes: Images of supermarket shelves containing multiple products.

### Functions and Their Descriptions
- `FeatureMatch()`: Matches key points between model and scene images using SIFT and a FLANN-based matcher.
- `Output()`: Displays the detection results, including product names, instance counts, dimensions, and positions.
- `display_model_images()`: Visualizes the model images being considered for detection.

## References
Refer to the OpenCV documentation and various tutorials on Feature Extraction, Image Classification, Generalized Hough Transform, and Hough Transform for foundational concepts applied in this project.
