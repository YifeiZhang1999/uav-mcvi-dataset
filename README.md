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

The scripts directory is optional and will contain utility scripts as they become available.

## Data Format and Access

The raw sensor measurements are provided as ROS 2 bags and hosted on Zenodo. The bag files are organized by environment and sequence.

- **Zenodo dataset:** [Zenodo DOI / Dataset URL]

This GitHub repository provides sensor calibration files, topic descriptions, sequence information, and utility scripts.

The ROS 2 bag files can be inspected and played using the standard ROS 2 bag tools. Please refer to the documentation for sensor topics and calibration details.

## Citation

If you use this dataset in your research, please cite the dataset using its Zenodo DOI:

```bibtex
@dataset{uav_mcvi_dataset,
  author    = {Author Names},
  title     = {UAV-MCVI: A Multi-Camera Visual-Inertial Dataset for UAV Close-Proximity Inspection},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {YOUR_ZENODO_DOI},
  url       = {https://doi.org/YOUR_ZENODO_DOI}
}
```

Please replace the placeholder fields with the actual metadata provided by Zenodo.

## License

The dataset is released under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

## Acknowledgments

We thank the relevant facilities and personnel who supported the data collection experiments.