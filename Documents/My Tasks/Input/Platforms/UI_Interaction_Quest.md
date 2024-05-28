> Author: TriHD
> 
> Last updated: 28-05-2024
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
![0-UI_Interaction_Diagram](../../../Images/Input/Quest/0-UI_Interaction_Diagram.png)

### Description
1. XRSynthesisLifetimeScope (VContainer)
````
- Đăng ký ICameraRig, ICameraRig được kế thừa bởi MetaQuestCameraRig.
- Đăng ký ICanvasRaycasterProvider, ICanvasRaycasterProvider được kế thừa bởi MetaQuestCanvasRaycasterProvider.
- Nhiệm vụ của MetaQuestCanvasRaycasterProvider là cung cấp raycast component cho UI để có thể tương tác.
````
