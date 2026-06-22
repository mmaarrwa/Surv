# Surv

Mobile sensing platform for a multi-robot land surveying swarm.

Runs on iPhones with LIDAR (12 pro and above), iphones without LIDAR.  
Provides obstacle detection, depth estimation, pose tracking, and origin marker detection over UDP to a ROS2/Nav2 navigation stack.

## Build
Built via Codemagic CI. Requires `SurveyingModel_v1.mlpackage` and `DepthAnythingV2SmallF16.mlpackage` placed in `Sources/AppModule/` before building.

## Models
- **SurveyingModel_v1** — custom YOLOv8n, 22 classes
- **DepthAnythingV2SmallF16** — monocular depth, CoreML F16, forced to `.cpuAndGPU`

## Notes
- Print `origin_marker.png` at 100% scale on A4. Measure printed width and update `markerPhysicalWidth` in `OriginManager.swift`.
- Neural Engine is intentionally disabled for the depth model (ANE freeze, Code=9).