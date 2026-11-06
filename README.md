# UAV-MCVI: A Multi-Camera Visual-Inertial Dataset for UAV Close-Proximity Inspection

## Overview

UAV-MCVI is a multi-camera visual-inertial dataset collected for research on UAV localization and visual-inertial odometry (VIO) in close-proximity inspection scenarios.

The dataset includes time-stamped image streams from four cameras, arranged as two oppositely oriented stereo pairs (front-view and rear-view), together with IMU measurements and auxiliary sensor data collected during indoor and outdoor UAV experiments. It covers challenging visual conditions encountered during close-proximity operations, including weak or repetitive textures, viewpoint-dependent visual degradation, restricted fields of view, and limited translational parallax.

The dataset is intended to support research on visual-inertial odometry, multi-camera state estimation, sensor fusion, visual observability analysis, and robust UAV localization. It can be used to evaluate different VIO and multi-camera estimation methods under challenging inspection conditions.

## Dataset Contents

- **Indoor sequences:** UAV experiments conducted in indoor environments with challenging visual and geometric conditions. VICON motion-capture measurements are available for ground-truth evaluation.
- **Outdoor sequences:** UAV close-proximity inspection experiments conducted around real-world building facades and surrounding environments.
- **Multi-camera measurements:** Image streams from two oppositely oriented stereo camera pairs, consisting of front-view and rear-view cameras.
- **IMU measurements:** Time-stamped inertial measurements recorded during the experiments.
- **Auxiliary sensor measurements:** GNSS and downward-facing laser rangefinder measurements are provided where available.
- **Calibration parameters:** Camera intrinsic and extrinsic parameters, IMU configuration, and auxiliary sensor extrinsic information.
- **ROS 2 bags:** Recorded sensor measurements provided in ROS 2 bag format.

The availability of auxiliary measurements and ground-truth data may vary between sequences. Please refer to the sequence descriptions for details.

## Sensor Configuration

The primary sensor configuration consists of:

- Four infrared cameras configured as two stereo pairs:
  - Front-view stereo pair
  - Rear-view stereo pair
- One onboard IMU
- Auxiliary GNSS receiver and downward-facing laser rangefinder, where available
- VICON motion-capture system for indoor ground-truth measurements

The body coordinate frame follows the convention:

- X-axis: Forward
- Y-axis: Left
- Z-axis: Upward

Camera intrinsic and extrinsic parameters, together with other sensor configuration files, are provided in the `config/` directory.

## Repository Structure

```text
UAV-MCVI/
├── README.md
│
├── config/
│   ├── sensors.yaml
│   ├── imu/
│   │   └── imu.yaml
│   ├── cameras/
│   │   ├── camera_intrinsics.yaml
│   │   └── camera_extrinsics.yaml
│   ├── rangefinder/
│   │   └── laser_rangefinder.yaml
│   └── ground_truth/
│       └── vicon.yaml
│
└── sequences/
    ├── indoor/
    │   └── sequences.yaml
    └── outdoor/
        └── sequences.yaml

```

## Data Format and Access

The raw sensor measurements are provided as ROS 2 bags. The bag files are organized by environment and sequence.

### Dataset Download

The complete dataset, including indoor and outdoor recordings, is available at:

- **[Download UAV-MCVI Dataset](https://drive.google.com/drive/folders/1S9JlLEAYyuNpzdwk8oRN5-4xzk5lV_Q9?usp=sharing)**

The released dataset includes recordings from both autonomous and manually piloted UAV flights, covering a broader range of trajectories and experimental scenarios beyond those presented in the paper.

Please refer to the corresponding `sequences.yaml` files for detailed sequence descriptions and data availability.

## License

The dataset is released under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.
