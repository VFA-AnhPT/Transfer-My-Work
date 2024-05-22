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
- Đăng ký NetworkConnectController như là một entry point (thực thi như là một monobehaviour).
- Entry point này sẽ chạy liên tục trong suốt qua trình xử lý network.
````

2. NetworkConnectController (Presenter - Control Flow)
````
- Dùng message pipe để broastcast tới NetworkConnectAreaTrigger. 
- Đợi sự kiện player đi vào vùng có thể connect vào network.
- Khi sự kiện trên được kích hoạt, bắt đầu connect và join room thông qua interface INetworkManager (đã injected bằng VContainer)
```` 

3. NetworkConnectAreaTrigger (Domain)
````
- Dùng message pipe để lắng nghe sự kiện từ NetworkConnectController.
````

4. INetworkManager (PhotonManger/FishNetManager) (Domain)
````
- Sau khi player kết nối vào room thành công, tạo ra một bản thể khác của nhân vật bằng prefab Vi_PhotonPlayer hoặc Vi_FishNetPlayer.
- Bản thể này dùng làm trung gian để sync data (transform, anim, hand tracking...)
- Data được sync qua lại giữa local player và remote player (cả local và remote player đều được tạo ra từ prefab WXR_Player Variant (đính kèm trong NetworkSettings))
````

5. Domain Photon/Domain Fishnet
-  Gồm những component đính kèm vào Vi_PhotonPlayer hoặc Vi_FishNetPlayer, dùng để sync data của player (WXR_Player Variant)
````
[Photon]
- PhotonPlayer.cs
- AvatarAnimationSync.cs
- TrackingModeSync.cs
- HandPoseSync.cs

[Fishnet]
- FishNetPlayer.cs
- FishNetAvatarAnimationSync.cs
- FishNetTrackingModeSync.cs
- FishNetHandPoseSync.cs
````
