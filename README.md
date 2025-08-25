# Distance Estimation of Robot Using IMU Data - Deep Learning Approach

## Overview
This project implements a deep learning solution for estimating the distance traveled by a robot using IMU (Inertial Measurement Unit) sensor data. Building upon traditional machine learning approaches from Part 1, this implementation uses a hybrid CNN-GRU neural network architecture to capture both spatial and temporal patterns in sensor data for improved distance prediction.

## Dataset
The dataset consists of CSV files recording robot motions at different speeds and paths:
- `straight_slow_Accelerometer.csv`
- `straight_fast_Accelerometer.csv` 
- `curve_slow_Accelerometer.csv`
- `curve_fast_Accelerometer.csv`

Each file contains sensor data collected using the Sensor Logger Android app, with the robot moving in segments for distance estimation.

## Model Architecture
**Hybrid CNN-GRU Model:**
- **Input Layer**: Accepts sequential IMU data (time steps × features)
- **CNN Layers**: Two 1D convolutional layers with ReLU activation for spatial feature extraction
- **Global Pooling**: Reduces feature dimensionality
- **GRU Layers**: Two Gated Recurrent Unit layers for capturing temporal dependencies
- **Output Layer**: Single neuron for distance regression

## Features
- **Data Preprocessing**: Normalization, smoothing, and resampling of sensor data
- **Data Augmentation**: Jittering, scaling, and time-warping techniques
- **Hybrid Architecture**: Combines CNN spatial feature extraction with GRU temporal modeling
- **Comparative Analysis**: Includes Random Forest and SVR models for performance comparison
- **Visualization**: Training loss curves and prediction vs actual distance plots

## Requirements
```bash
pip install torch pandas numpy scikit-learn scipy matplotlib
```

## Project Structure
```
├── robot_distance_estimation_DL.py      # Main implementation script
├── sample_data/
│   ├── A3Data/                # Training data directory
│   └── A4Data/                # Test data directory
├── README.md                  # This file
└── requirements.txt           # Python dependencies
```

## Usage
1. Place your sensor data in the appropriate directories:
   - Training data: `/content/sample_data/A3Data/`
   - Test data: `/content/sample_data/A4Data/`

2. Run the main script:
```bash
python robot_distance_estimation_DL.py
```

3. The script will:
   - Preprocess and augment the data
   - Train Random Forest, SVR, and CNN-GRU models
   - Evaluate performance using MAE and RMSE metrics
   - Generate visualization plots

## Results
The hybrid CNN-GRU model demonstrates improved performance over traditional machine learning approaches by effectively capturing both spatial and temporal patterns in IMU data.

## Key Features
- **Data Processing**: Comprehensive preprocessing pipeline with normalization and smoothing
- **Model Comparison**: Side-by-side evaluation of traditional ML and deep learning approaches
- **Visual Analytics**: Training progression and prediction accuracy visualization
- **Modular Design**: Easy to extend with additional models or preprocessing techniques

## Contributors
- Rutul Hemantkumar Trivedi 
- Tom-Ayegunle Taiwo Anuoluwapo 

## License
Academic project for CPSC-5616EL course at Laurentian University.
