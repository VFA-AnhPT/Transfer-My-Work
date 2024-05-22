> Author: TriHD
> 
> Last updated: 21-05-2024
> 
> [Vietnamese]
# Hand Tracking For Mobile

## Related Platforms
Platform   |Notes       
----------------|------------
[Quest](./Platforms/HandTracking_Quest.md)|Hand tracking for Quest.
[Vive](./Platforms/HandTracking_Vive.md)|Hand tracking for Vive.

## Flow
### Diagram
![0-HandTrackingDiagram](../../Images/HandTracking/0-HandTrackingDiagram.png)

### Description
1. XRSynthesisLifetimeScope (VContainer)
````
- Đăng ký ICameraRig, ICameraRig được kế thừa bởi MobileCameraRig.
- Đăng ký IVRModeProvider, IVRModeProvider được kế thừa bởi MobileVRModeProvider.
````

2. Domain (XR)
````
- MobileCameraRig dùng để thiết lập tracking cho VR (head, left/right hand,....) và xử lý input từ VR.
- MobileVRModeProvider dùng để kiểm soát những phần xử lý khi chuyển đổi qua lại giữa non-VR mode và VR mode.
```` 

3. Domain (Hand Tracking) 
````
- Dùng message pipe để lắng nghe sự kiện từ NetworkConnectController.
````
