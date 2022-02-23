# mobio-facial-analysis

## [NOTE: This repo is a WIP. Will be continuing cleanup and documentation throughout this week.]

There are two main submodules in this repo. 
- `mediapipe` contains the code for running the demo on Android and C++. The Android demo is the same as last term, the code hasn't been updated. I've started putting together a standalone demo in C++ to make integration easier. This is still ongoing, and I'm hoping to wrap it up by the end of this week.
- `MediaPipeUnityPlugin` contains demo code for building and running the demo in Unity and to deploy it on Android/iOS devices.
- Core C++ Demo code can be found in `mediapipe/graphs/mobio`

### To build C++ Demo:
`bazel build -c opt --define MEDIAPIPE_DISABLE_GPU=1 media^Cpe/examples/desktop/face_mesh:face_mesh_cpu_mobio`

### To run C++ Demo:
`GLOG_logtostderr=1 bazel-bin/mediapipe/examples/desktop/face_mesh/face_mesh_cpu_mobio --calculator_graph_config_file=mediapipe/graphs/face_mesh/face_mesh_desktop_live_mobio.pbtxt`

<img width="1200" alt="image" src="https://user-images.githubusercontent.com/16181437/155107737-e4327c58-1973-47b9-9f4e-2471079a3c0e.png">


<img width="1211" alt="image" src="https://user-images.githubusercontent.com/16181437/155108128-9f71e8d7-ac40-4afc-9ab7-f41006eef98e.png">
