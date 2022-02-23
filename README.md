# mobio-facial-analysis

There are two main submodules in this repo. 
- `mediapipe` contains the code for running the demo on Android and C++. The Android demo is the same as last term, the code hasn't been updated.
- `mediapipe/graphs/mobio` contains the core source C++ files for performing facial analysis. 
- The main C++ demo entry point can be found in `mediapipe/examples/desktop/mobio`.
- `MediaPipeUnityPlugin` contains demo code for building and running the demo in Unity and to deploy it on Android/iOS devices.

### To build C++ Demo:
`bazel build -c dbg --define MEDIAPIPE_DISABLE_GPU=1 mediapipe/examples/desktop/mobio:mobio_facial_analysis`

### To run C++ Demo:
`GLOG_logtostderr=1 bazel-bin/mediapipe/examples/desktop/mobio/mobio_facial_analysis --calculator_graph_config_file=mediapipe/graphs/mobio/facial_analysis_desktop_live.pbtxt`

The core facial analysis architecture is executed by the subgraph `MobioResultProcessor`. The following diagram shows how `MobioResultProcessor` fits within the larger facial analysis system:

![image](https://user-images.githubusercontent.com/16181437/155273958-af054653-4e1c-42b4-bd31-cd5fb199dc51.png)

The following diagram provides a more in-depth view of `MobioResultProcessor`.
![image](https://user-images.githubusercontent.com/16181437/155273790-25c7fec1-99bb-4cbe-8c0f-5054e6f3f3b6.png)
