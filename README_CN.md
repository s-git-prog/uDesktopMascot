# uDesktopMascot

[![Unity 版本](https://img.shields.io/badge/Unity-6000.0%2B-blueviolet?logo=unity)](https://unity.com/releases/editor/archive)
[![版本发布](https://img.shields.io/github/release/MidraLab/uDesktopMascot.svg)](https://github.com/MidraLab/uDesktopMascot/releases)
[![Unity 测试 CI](https://github.com/MidraLab/uDesktopMascot/actions/workflows/edit-test.yml/badge.svg)](https://github.com/MidraLab/uDesktopMascot/actions/workflows/edit-test.yml)

日本語 | [English](README_EN.md) | [中文](README_CN.md) | [Español](README_ES.md) | [Français](README_FR.md)

**注意**: 上述语言（English、中文、Español、Français）是由GPT-4o-mini自动翻译生成的。翻译的准确性和细微差别请参见原文（日本語）。

<!-- TOC -->
* [uDesktopMascot](#udesktopmascot)
  * [概述](#概述)
  * [功能列表](#功能列表)
  * [在macOS上的运行](#在macos上的运行)
  * [要求](#要求)
  * [许可](#许可)
  * [素材说明](#素材说明)
  * [创建安装程序的方法](#创建安装程序的方法)
    * [Windows](#windows)
    * [macOS](#macos)
  * [创作者鸣谢](#创作者鸣谢)
  * [第三方通知](#第三方通知)
  * [赞助商](#赞助商)
<!-- TOC -->

## 概述

“uDesktopMascot”是一个以`创造的自由化`为主题的桌面吉祥物应用程序的开源项目。
其功能示例包括加载VRM和GLB/FBX格式的模型，并在桌面上显示。此外，还可以自由设置菜单界面和应用程序窗口等GUI的颜色和背景图像。
详细功能列表请参见 [功能列表](#功能列表)。

![](Docs/Image/AppImage.png)

**支持平台**
* Windows 10/11
* macOS

## 功能列表

该应用程序实现了以下功能。详细信息请参见以下列表。

外部资源的添加可以通过将其放置在StreamingAssets文件夹中来实现。

<details>

<summary>模型・动画</summary>

* 读取并显示放置在StreamingAssets中的任何模型文件。
  * 支持VRM(1.x, 0.x)格式的模型。
  * 支持GLB/GLTF格式的模型。(不支持动画)
  * 支持FBX格式的模型。(但某些模型的纹理无法加载，动画也不支持)
    * 纹理可以通过放置在StreamingAssets/textures/中来加载。
* 从模型选择・添加界面添加VRM模型
  * 通过指定路径进行添加
  * 从文件选择对话框中进行添加

</details>

<details>

<summary>语音・背景音乐</summary>

* 读取并播放放置在SteamingAssets/Voice/中的音频文件。如果有多个，将随机播放。
  * 点击时播放的音频来自于放置在StreamingAssets/Voice/Click/中的音频文件。 
* 读取并播放放置在SteamingAssets/BGM/中的音乐文件。如果有多个，将随机播放。
* 添加角色的默认语音
  * 默认语音使用[COEIROINK:つくよみちゃん](https://coeiroink.com/character/audio-character/tsukuyomi-chan)的音频。
  * 在应用启动时、应用退出时、点击时播放。

</details>

<details>

<summary>通过文本文件进行应用程序设置</summary>

可以通过application_settings.txt文件来更改应用程序的设置。

设置文件的结构如下：

```txt
[Character]
ModelPath=default.vrm
TexturePaths=test.png
Scale=3
PositionX=0
PositionY=0
PositionZ=0
RotationX=0
RotationY=0
RotationZ=0

[Sound]
VoiceVolume=1
BGMVolume=0.5
SEVolume=1

[Display]
Opacity=1
AlwaysOnTop=True

[Performance]
TargetFrameRate=60
QualityLevel=2
```

</details>

<details>

<summary>菜单界面</summary>

* 可以设置菜单界面的背景图像及背景颜色。
  * 背景图像可以从放置在StreamingAssets/Menu/中的图像文件中读取。支持的图像格式包括：
    * PNG
    * JPG(JPEG)
    * BMP
    * GIF（静态图像）
    * TGA
    * TIFF
  * 背景色可以指定颜色代码。
* 从菜单界面可访问以下功能：
  * 模型选择・添加界面
  * AI聊天功能
  * LocalWeb功能
  * 应用设置
  * 退出应用程序
* 按下菜单界面的隐藏按钮，可以在Windows系统中将应用程序缩至通知区域。
  * 被缩至的应用程序可以通过点击通知区域的图标重新显示。

</details>

## 在macOS上的运行

在macOS上运行应用程序时，GateKeeper可能会阻止应用程序。
在这种情况下，请在终端中执行以下命令。

```sh
xattr -r -c uDesktopMascot.app
```

## 要求
* Unity 6000.0.31f1 (IL2CPP)

## 许可
* 代码依据[Apache License 2.0](LICENSE)进行许可。
* 以下资源依据[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)进行许可。
  * 背景音乐
  * 模型

## 素材说明
* 默认角色动画使用[『VRMお人形遊び』用动画数据合集](https://fumi2kick.booth.pm/items/1655686)制作。已确认可以包含并分发在该库中。
* 字体为[Noto Sans Japanese](https://fonts.google.com/noto/specimen/Noto+Sans+JP?lang=ja_Jpan)。根据[SIL OPEN FONT LICENSE Version 1.1](https://fonts.google.com/noto/specimen/Noto+Sans+JP/license?lang=ja_Jpan)重新分发Noto Sans JP字体。字体的版权归原作者（Google）所有。
* 默认语音使用[COEIROINK:つくよみちゃん](https://coeiroink.com/character/audio-character/tsukuyomi-chan)的音频。关于使用方法，已事先向COEIROINK确认。
* 按钮图标使用[MingCute](https://github.com/MidraLab/MingCute)。

## 创建安装程序的方法
### Windows
* 在Unity中将项目构建到名为`uDesktopMascot`的文件夹。

* 安装[Inno Setup](https://www.jrsoftware.org/isdl.php)。
  
* 打开后，点击`More files`，选择项目下的`setup.iss`文件。
  
![](Docs/Image/SetupIss-1.png)
* 选择后，点击播放按钮。
  
![](Docs/Image/SetupIss-2.png)
* 构建完成后，安装程序将在项目的根目录生成。

### macOS
仅能在macOS电脑上创建安装程序。

* 在Unity中将项目构建到名为`uDesktopMascot`的文件夹。

* 执行以下命令。
```sh
cd build
productbuild --component uDesktopMascot/uDesktopMascot.app /Applications ./uDesktopMascot_mac_installer.pkg
```
* 构建完成后，`build`文件夹中将生成`uDesktopMascot_mac_installer.pkg`。

## 创作者鸣谢
* 模型: “アオゾラ”样
* 背景音乐: MidraLab(eisuke)
* 软件图标: やむちゃ样

## 第三方通知

请参见[NOTICE](./NOTICE.md)。

## 赞助商
- Luna
- uezo