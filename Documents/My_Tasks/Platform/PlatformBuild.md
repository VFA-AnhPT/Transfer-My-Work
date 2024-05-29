> Author: TriHD
> 
> Last updated: 29-05-2024
> 
> [Vietnamese]
# Platform Build
## Quest
1. <ins><b>Lỗi không cài được apk vào Hub</b></ins>
- Sau khi build app và cài apk thông qua Meta Quest Developer Hub. Đôi khi sẽ gặp lỗi cài đặt như sau:
  - Lỗi 1: Quá trình cài đặt không bao giờ kết thúc và xuất hiện line đỏ.
  ![0_BuildQuest_0_Stuck_1](../../Images/PlatformBuild/Quest/0_BuildQuest_0_Stuck_1.png) 
  - Lỗi 2: Quá trình cài đặt bị kết thúc giữa chừng.
    
  ![0_BuildQuest_1_Stuck_2](../../Images/PlatformBuild/Quest/0_BuildQuest_1_Stuck_2.gif)

- Cách xử lý:
  - Đổi package name thành một tên khác và thử lại.
  ![0_BuildQuest_2_Fix_Stuck](../../Images/PlatformBuild/Quest/0_BuildQuest_2_Fix_Stuck.png)

## Mobile
1. <ins><b>Lỗi không build được file apk</b></ins>
- Đôi khi sẽ gặp tình trạng lỗi như sau:
  
  ![0_BuildMobile_0_Stuck_1](../../Images/PlatformBuild/Mobile/0_BuildMobile_0_Stuck_1.png) 

- Cách xử lý:
  - Xóa toàn bộ folder chứa plugin Android của AVProVideo như hình:
  ![0_BuildMobile_1_Fix_Stuck_1](../../Images/PlatformBuild/Mobile/0_BuildMobile_1_Fix_Stuck_1.png)
  - Khi hoàn tất task và switch sang một branch khác thì nhớ reset lại tránh xóa luôn.
 
