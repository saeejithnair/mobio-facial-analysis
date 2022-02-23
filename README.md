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

<img width="1200" alt="image" src="https://user-images.githubusercontent.com/16181437/155107737-e4327c58-1973-47b9-9f4e-2471079a3c0e.png">


<img width="1211" alt="image" src="https://user-images.githubusercontent.com/16181437/155108128-9f71e8d7-ac40-4afc-9ab7-f41006eef98e.png">
