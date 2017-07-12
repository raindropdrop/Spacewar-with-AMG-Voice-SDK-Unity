# Spacewar with AMG Voice SDK Unity

*Read this in other languages: [English](README.en.md)*

这个开源示例项目演示了如何在 Unity3D 中集成Agora游戏SDK，实现在游戏中的音频通话。

在这个示例项目中包含了以下功能：

- 加入通话和离开通话；
- 选择语音模式：自由模式、指挥模式、听众模式；
- 静音和取消静音；
- 音乐混音和播放音效；
- 语音变声效果；
- 音效和语音的方位感；
- 设置语音、混音和音效的音量；

你也可以在这里查看入门版的示例项目：[Hello-Unity3D-Agora](https://github.com/AgoraIO/Hello-Unity3D-Agora)

Agora游戏SDK支持 iOS / Android / Unity3D / Cocos2d 等多个平台，你可以查看对应各平台的示例项目：

- [Spacewar-with-AMG-Voice-SDK-SpriteKit](https://github.com/AgoraIO/Spacewar-with-AMG-Voice-SDK-SpriteKit)
- [Spacewar-with-AMG-Voice-SDK-Cocos2d](https://github.com/AgoraIO/Spacewar-with-AMG-Voice-SDK-Cocos2d)

## 运行示例程序
首先在 [Agora.io 注册](https://dashboard.agora.io/cn/signup/) 注册账号，并创建自己的测试项目，获取到 AppID。将 AppID 填写进 ApplicationModel.cs

```
static public string AppId = "YOUR APP ID";
```

然后在 [Agora.io SDK](https://www.agora.io/cn/blog/download/) 下载 **AMG 游戏语音SDK**，解压后

- 把SDK中 **libs/Android/** 下的内容，复制到项目的 **Assets/Plugins/Android/AgoraAudioKit.plugin/libs/** 文件夹下
- 把SDK中 **libs/iOS/** 下的内容，复制到项目的 **Assets/Plugins/iOS/** 文件夹下
- 把SDK中 **libs/Scripts/AgoraGamingSDK/** 下的内容，复制到项目的 **Assets/Scripts/AgoraGamingSDK/** 文件夹下

最后使用 Unity 打开本项目即可运行。

## 运行环境
* Unity 5.5 +

## 联系我们

- 完整的 API 文档见 [文档中心](https://docs.agora.io/cn/)
- 如果在集成中遇到问题, 你可以到 [开发者社区](https://dev.agora.io/cn/) 提问
- 如果有售前咨询问题, 可以拨打 400 632 6626，或加入官方Q群 12742516 提问
- 如果需要售后技术支持, 你可以在 [Agora Dashboard](https://dashboard.agora.io) 提交工单
- 如果发现了示例代码的bug, 欢迎提交 [issue](https://github.com/AgoraIO/Spacewar-with-AMG-Voice-SDK-Unity/issues)

## 代码许可

The MIT License (MIT).

Before building, you need to
1. Unzip AMG Voice Unity SDK. If you dont have one, please contact sales@agora.io

[c# interface files]
Copy c# scripts from libs/Scripts/*.cs to Assets/AgoraGamingSDK/
  AgoraGamingRtcEngine.cs    Engine c# wrapper
  AudioEffectManager.cs      Audio effect manager, used to fine tune audio effects
  videoSurface.cs            Video surface, used to render video (local and remote)

[iOS support]
Copy files from libs/Plugins/iOS/* to Assets/Plugins/iOS/
  AgoraRtcEngineKit.framework    Core Agora sdk
  libagoraSdkCWrapper.a          Wrapper library

[Android support]
Copy files from libs/Plugins/Android/libs/* to Assets/Plugins/Android/libs/
  agora-unity-wrapper.jar
  libs/agora-rtc-sdk.jar
  armeabi-v7a/
  x86/

2. Edit AppId in Assets/MainScene/Scripts/ApplicationModel.cs. You can get your App ID at https://dashboard.agora.io

3. Ensure that your environment meet the following requirements:
* Unity 5.5 or later
* Xcode 8.0 or later
* 2 or more real iOS devices (9.0 or later) with audio functions

4. For Android, appropriate permissions are requested. There's a example AndroidManifest.xml in the package

5. For iOS, add VideoTool.frameworks and resolv.tbd to your project

6. For video support, disable Auto Graphics API and choose OpenGLES2
