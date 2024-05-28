> Author: TriHD
> 
> Last updated: 24-05-2024
> 
> [Vietnamese]
# Hand Tracking For Vive

## Related Platforms
Platform   |Notes       
----------------|------------
[Mobile](../HandTracking.md)|Hand tracking for Mobile.
[Quest](./HandTracking_Quest.md)|Hand tracking for Quest.

## Flow
### Diagram
![0-HandTrackingDiagram](../../../Images/HandTracking/Vive/0-HandTrackingDiagram.png)

### Description
1. XRSynthesisLifetimeScope (VContainer)
````
- Đăng ký ICameraRig, ICameraRig được kế thừa bởi ViveCameraRig.
- Đăng ký HandPoseController như một entry point và cập nhật xuyên suốt.
````

2. Domain (XR)
````
- ViveCameraRig dùng để thiết lập tracking cho VR (head, left/right hand,....) và xử lý input từ VR.
- Tracking VR (head, left/right hand,....) sẽ được xử lý thông qua Domain (Hand Tracking).
````
![1-Flow_1_DomainXR](../../../Images/HandTracking/Vive/1-Flow_1_DomainXR.png)

3. Domain (Hand Tracking) 
- <ins>HandManager</ins>
````
- Khởi tạo XR Device cùng với những settings thiết lập ban đầu.
````
![1-Flow_2_HandManager](../../../Images/HandTracking/Vive/1-Flow_2_HandManager.png)

- <ins>HandMeshRenderer</ins>
````
- Chứa thông tin BoneMap (liên kết giữa xương cha và xương con bằng bone id).
- Khởi tạo và truy xuất bone poses và bind bone poses của tay.
  + WaveBone_1 là bone poses.
  + WaveBone_1_bindpose là bind bone poses.
````
![1-Flow_4_HandBind_BonePoses_1](../../../Images/HandTracking/Vive/1-Flow_4_HandBind_BonePoses_1.png)
![1-Flow_5_HandBind_BonePoses_2](../../../Images/HandTracking/Vive/1-Flow_5_HandBind_BonePoses_2.png)

- <ins>CustomGestureProvider</ins>
````
- Dùng để apply những gesture được thiết lập sẵn bằng settings.
````

## Apply Calculated Hand Tracking Data To Avatar's Hand Model
- <ins>HandPoseBuilder</ins>
````
- Thực hiện việc build mới một humanoid avatar bằng cách:
  + Xây khung xương body từ root.
  + Xây khung xương hand và fingers (fingers dùng bind bone poses để xây).
- Áp dụng local rotation đến từ bone poses được build từ HandMeshRenderer.
- Chuyển đổi humanoid avatar thành pose handler để tính toán giá trị pose muscles sau này ở HandPoseInterpolator.
````

- <ins>HandPoseInterpolator</ins>
````
- Cập nhật hand pose của cả 2 tay.
- Giá trị hand pose của từng tay sẽ là tổng pose muscles mặc định (từ config) và pose muscles từ hand pose builder cộng lại.
````
![1-Flow_6_HandPoseInterpolator](../../../Images/HandTracking/Vive/1-Flow_6_HandPoseInterpolator.png)

## Enable Virtual Vive Hand Renderer
![1-Flow_3_HandMeshRender](../../../Images/HandTracking/Vive/1-Flow_3_HandMeshRender.png)
