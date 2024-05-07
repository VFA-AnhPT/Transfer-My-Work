> Author: TriHD
> 
> Last updated: 08-05-2024
> 
[English/[Vietnamese](../PlatformSwitcher.md)]
# Overview

## Switch platform
 
- The XRSynthesis.Multiplatform function is intended to collectively change settings for Unity build targets, packages, camera rigs, XR Plugin Management plugins, player settings, game settings (ex: HandPoseSettings, InitializeObjectAsset,...).
- Be sure to switch the platform from this menu, not from Unity's Build Settings:

  > XRSynthesis/Multiplatform/Switch/<target_platform>

![SwitchPlatforms](../../Images/PlatformSwitcher/0-SwitchPlatforms.png)

Currently we are working on the following platforms
````
- Quest
- Vive
- Windows (OpenXR) (Meta Quest)
- Mobile (Android/iOS)
````

Further platforms to work on 
````
- Apple Vision Pro
````

## XRSynthesis Settings

1. When switching platforms, there are some changes that will occur in the settings within the XRSynthesis prefab.

![XRSynthesisPrefab](../../Images/PlatformSwitcher/2-XRSynthesisPrefab.png)

2. These settings below will change
````
- HandPoseSettings
- CameraRigSettings
- AvatarInitializeSettingsScriptable
- InitializeObjectAsset
````

![XRSynthesisSettings](../../Images/PlatformSwitcher/2-XRSynthesisSettings.png)

3. About AvatarInitializeSettingsScriptable
```` 
- AvatarVRIKDataSetting will be changed.
- AvatarVRIKDataSetting is used to store IK Anchor data for the avatar body (head, hand, chest,...) when using controller or hand tracking.
````

![AvatarInitializeSettingsScriptable](../../Images/PlatformSwitcher/3-AvatarInitializeSettingsScriptable.png)

4. About CameraRigSettings
```` 
- Camera rig prefab will be replaced.
- Camera rig prefab will be used to setup VR components (VR camera, VR tracking mode, VR input...) for the current platform.
````    

![CameraRig](../../Images/PlatformSwitcher/3-CameraRig.png)

5. About HandPoseSettings
````
- HandTrackingPose asset will be changed.
- HandTrackingPose asset is to apply initial finger poses for both hands when using hand tracking.
- The Hand Poses section is to apply finger poses for specific actions when using the controller.
````

![HandPoseSettings](../../Images/PlatformSwitcher/3-HandPoseSettings.png)

6. About InitializeObjectAsset
````
- Assgin essential prefabs to handle UI, event system, data manager and so on.
````
![3-InitializeObjectAsset](../../Images/PlatformSwitcher/3-InitializeObjectAsset.png)


## 3.	Platform Packages
When switching to any platform, essential packages will be installed from two sources
````
- Install from LocalPackages
- Install from Unity Package Manager with package name automatically
````

1. Install from LocalPackages
   
![1-LocalPackages_](../../Images/PlatformSwitcher/1-LocalPackages_.png)

- LocalPackages folder content
![1-LocalPackages](../../Images/PlatformSwitcher/1-LocalPackages.png)

````
- Each platform will require its own packages
Ex:
[Quest]
    + XRSynthesis.Multiplatform.MetaQuest (from LocalPackages)
    + Oculus XR Plugin (from package manager with package name com.unity.xr.oculus@4.0.0)

[Vive]
    + XRSynthesis.Multiplatform.Vive (from LocalPackages)
    + ViveWaveXR/WaveEssence (from LocalPackages)
    + ViveWaveXR/WaveNative (from LocalPackages)
    + ViveWaveXR/WaveXRSdk (from LocalPackages)
````

## Project Settings
Each platform will perform these changes below and they will be different from others

1. Custom Build

![5-CustomBuild](../../Images/PlatformSwitcher/5-CustomBuild.png)

2. Graphic Api

![5-GraphicApi](../../Images/PlatformSwitcher/5-GraphicApi.png)

3. Platform Data

![5-PlatformData](../../Images/PlatformSwitcher/5-PlatformData.png)

4. Player Platform Settings

![5-PlayerPlatformSettings](../../Images/PlatformSwitcher/5-PlayerPlatformSettings.png)

5. Script Define Symbol

![5-ScriptDefineSymbol](../../Images/PlatformSwitcher/5-ScriptDefineSymbol.png)

6. Targe/Minimum Api Level
![5-TargerAndMinimumApi](../../Images/PlatformSwitcher/5-TargerAndMinimumApi.png)

## Implementation
````

````
