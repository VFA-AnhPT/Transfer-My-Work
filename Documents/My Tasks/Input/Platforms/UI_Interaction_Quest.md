> Author: TriHD
> 
> Last updated: 27-05-2024
> 
> [Vietnamese]
# UI Interaction For Quest

## Related Platforms
Platform   |Notes       
----------------|------------
[Common](../Input.md)|Input for all platforms.
[Vive](./UI_Interaction_Vive.md)|UI interaction for Vive.

## Flow
### Diagram
![0-HandTrackingDiagram](../../../Images/HandTracking/Quest/0-HandTrackingDiagram.png)

### Description
1. XRSynthesisLifetimeScope (VContainer)
````
- Đăng ký ICameraRig, ICameraRig được kế thừa bởi MetaQuestCameraRig.
- Đăng ký HandPoseController như một entry point và cập nhật xuyên suốt.
````
