# mobio-facial-analysis

## Overview
There are two main submodules in this repo. 
- [mediapipe](https://github.com/saeejithnair/mediapipe/tree/snair/main) contains the code for running the demo on Android and C++. The Android demo is the same as last term, the code hasn't been updated.
- `MediaPipeUnityPlugin` contains demo code for building and running the demo in Unity and to deploy it on Android/iOS devices.

Of these, the most useful code to start with is the facial analysis demo that was ported to C++.
- [mediapipe/graphs/mobio](https://github.com/saeejithnair/mediapipe/tree/snair/main/mediapipe/graphs/mobio) contains the core source C++ files for performing facial analysis. 
- The main C++ demo entry point can be found in [mediapipe/examples/desktop/mobio](https://github.com/saeejithnair/mediapipe/tree/snair/main/mediapipe/examples/desktop/mobio).

## Usage
### To build C++ Demo:
`bazel build -c opt --define MEDIAPIPE_DISABLE_GPU=1 mediapipe/examples/desktop/mobio:mobio_facial_analysis`

### To run C++ Demo:
`GLOG_logtostderr=1 bazel-bin/mediapipe/examples/desktop/mobio/mobio_facial_analysis --calculator_graph_config_file=mediapipe/graphs/mobio/facial_analysis_desktop_live.pbtxt`

## Architecture
The core facial analysis architecture is executed by the subgraph `MobioResultProcessor`. The following diagram shows how `MobioResultProcessor` fits within the larger facial analysis system:

![image](https://user-images.githubusercontent.com/16181437/155273958-af054653-4e1c-42b4-bd31-cd5fb199dc51.png)

The following diagram provides a more in-depth view of `MobioResultProcessor`. The subgraph currently executes two calculators.
- `MobioContourCalculator` which can be found in `mediapipe/graphs/mobio/calculators/mobio_contour_calculator.cc`
- `MobioIntensityCalculator` which can be found in `mediapipe/graphs/mobio/calculators/mobio_intensity_calculator.cc`
![image](https://user-images.githubusercontent.com/16181437/155273790-25c7fec1-99bb-4cbe-8c0f-5054e6f3f3b6.png)

## TODOs
- Port over the contour radius calculator `MobioRadiusCalculator`
- Extend support to measure pupil dilation.
