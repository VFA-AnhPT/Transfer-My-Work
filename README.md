# XRSynthesis

This is a VR project platform made by Frame Synthesis Co., Ltd. made by Unity.

It acts as a standalone walkthrough sample that works on each platform.

-XRSynthesis.Core
-XRSynthesis.Multiplatform
-XRSynthesis.World

I have the above built-in package and it is referenced in manifest.json as below.

````
     "com.framesynthesis.xrsynthesis.core": "https://github.com/FrameSynthesis/XRSynthesis.git?path=Packages/com.framesynthesis.xrsynthesis.core",
     "com.framesynthesis.xrsynthesis.multiplatform": "https://github.com/FrameSynthesis/XRSynthesis.git?path=Packages/com.framesynthesis.xrsynthesis.multiplatform",
     "com.framesynthesis.xrsynthesis.world": "https://github.com/FrameSynthesis/XRSynthesis.git?path=Packages/com.framesynthesis.xrsynthesis.world",
````

There are two main ways to develop a derivative project based on this base system: Choose the latter if you need to modify the base system itself.

- Duplicate this project and delete the embedded packages (com.framesynthesis.xrsynthesis.core folder, etc.) in the Packages folder
- Clone this repository to a new repository, add this repository remotely (upstream, etc.) in addition to origin, and merge accordingly

## About the project

For an overview of the project and how to build it, please refer to [Project file overview](Documents/ProjectOverview.md).

## Method of operation

PC: Move with arrow keys/WASD, jump with space
iPhone/Android: Move with virtual stick

Switch to subjective perspective with the camera button on the top left. Rotate by dragging the screen.

If you have a VR headset connected to your Quest or PC, press the VR button on the top right to enter VR mode. Move with the stick on the motion controller.