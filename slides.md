---
# You can also start simply with 'default'
theme: seriph
favicon: /img/favicon.png
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: ./android.gif
# some information about your slides (markdown enabled)
title:  安卓入门
info: false
author: Brian Yao<me@brianyao.tech>
# keywords field for exported PDF, comma-delimited.
keywords: 安卓入门
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
  enabled: dev
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
presenter: dev
record: dev
contextMenu: dev
---

# ***Android 入门***

## 2024/7/18

<style>
h1 {
  /*  字符笔画的宽和颜色  */
  -webkit-text-stroke: 3px #ffcb4e;
  /*  透明色  */
  color: rgba(0,0,0,0);
  /*  和 box-shadow 很像，给图像一个阴影  */
  filter: drop-shadow(0 0 3px rgb(249, 187, 3, 0.7)) drop-shadow(0 0 15px #f9bb03);
  /*  字母间更加紧凑  */
  letter-spacing: -.02em;
  margin: 0;
  padding: 20px 0;
  font-family: urbane-rounded;
  font-size: 100px;
}
h2 {
  color: #ff6859;
  text-shadow: 0 0 20px #ff6859;
  letter-spacing: -.02em;
  margin: 0;
  font-family: urbane-rounded;
}
</style>

--- #2
transition: fade-out
layout: section
---

# Android 介绍


--- #3
transition: fade-out
---

# 什么是 Android？

Android 是由 Google 开发的开源操作系统，主要用于智能手机、手表、车机、电视盒子等。它基于 Linux 内核，提供一个灵活的应用程序框架，支持广泛的硬件和软件功能。

<v-clicks>

- 开放源代码：代码由 [AOSP](https://android.googlesource.com/platform/manifest)（Android Open Source Project）托管，AOSP 是**大多数** ROM 的”底座“，允许开发者、制造商和运营商进行自定义和修改。
- 多任务处理：支持多任务处理，可以同时运行多个应用程序。
- 丰富的生态系统：通过谷歌商店或第三方商店，用户可以下载数以百万计的应用程序，并且支持侧载（sideloading），用户可以通过下载 APK 文件安装应用程序。
- 可定制用户界面： 用户可以通过更换主题、图标、小部件等来定制自己的设备。
- 集成的谷歌服务：谷歌GMS（Google Mobile Services）是谷歌为 Android 设备提供的一系列服务（Google Play、Gmail、YouTube、Google Maps、Google Drive 等等，并且提供了统一和直观的推送服务 FCM (Firebase Cloud Messaging)。

</v-clicks>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
如果要学习安卓源码，也是从 AOSP 开始，AOSP 包含了 Android 系统的源代码、编译脚本、文档等等。

大多数的 ROM 是基于 AOSP 的，例如国内的 MIUI（小米）、Flyme（魅族）、ColorOS（OPPO）、EMUI（华为发布鸿蒙前的系统，再之前叫 Emotion UI），国外的例如 One UI（三星）等等。他们是都是基于 AOSP 的，但它们不都只是基于安卓原生系统交互层进行改进，有些已深入系统底层的 Linux 内核，在系统框架、性能调度、内核能力做了大量的底层“魔改”。

之前提到这些 ROM 都可以称为制造商或运营商官方定制 ROM，如果想用原汁原味的安卓，可以选择 Google 官方的 Pixel 系列手机，这是最接近原生安卓的手机。但是 Pixel 系列手机在国内并不是很受欢迎，因为 Google 服务在国内无法使用。

对比 iOS，iOS 之前是不允许侧载的，但是应欧盟要求，随着苹果iOS 17.4 Beta 1 发布：27 个欧洲国家3 月将支持侧载、第三方应用市场、非WebKit 引擎浏览器等。

-->

--- #4
layout: two-cols-header
transition: fade-out
level: 2
---

# Android 的历史

::left::

<v-clicks>

- 初创与收购：Android 是由安迪·鲁宾（Andy Rubin）等人创立的公司 Android Inc. 开发的，2005 年被 Google 收购。
- 首次发布：2008 年 9 月 发布首个商业版本的 Android 系统，HTC Dream 是第一款搭载 Android 系统的手机。
- 命途多舛：由于在开源代码和内核修改上的分歧，安卓一度被 Linux 内核开发社区除名。由于 Android 的开发使用了 Java 语言，2010年甲骨文起诉谷歌指控安卓系统侵犯了 Java 的版权。
- 新宠诞生：JetBrains 发布了 Kotlin 语言，谷歌宣布 Kotlin 成为 Android 官方开发语言。
- 快速发展： 安卓数字版（10-15）陆续发布，取消甜点名称，聚焦隐私和性能优化

</v-clicks>

::right::

<v-click>
<div class="flex flex-col items-center justify-center">
  <img src="/img/andy.png" class="w-[70%] h-auto" />
  <p class="text-sm">安迪·鲁宾于2008年在日本举办谷歌开发者日活动</p>
</div>
</v-click>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #5
transition: fade-out
---
# Android 的历史版本

<img src="/img/android-version-history.png" class="w-full h-auto -mt-5 -ml-5" />

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #6
transition: fade-out
level: 2
---

# Android vs. iOS

<v-clicks>

| Android | iOS |
| --- | --- |
| 开放源代码 | 闭源 |
| 多任务处理 | 限制多任务 |
| 定制性强 | 封闭性强 |
| 多厂商支持 | 单一厂商 |
| 侧载应用 | 限制侧载 |
| 更新速度慢 | 更新速度快 |
| 安全性低 | 安全性高 |

</v-clicks>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
Android 和 iOS 从大版本更新频率上来讲大致相同都是一年一次。但是大版本的更新分发速度不同，这是因为 Android 的更新需要经过厂商的适配，而 iOS 的更新是由苹果直接发布的，所以 iOS 的更新速度要快于 Android。
 -->


--- #7
transition: fade-out
level: 2
---

# 全球移动操作系统市场份额

<a href="https://www.statista.com/statistics/272698/global-market-share-held-by-mobile-operating-systems-since-2009/" target="_blank">
  <img src="/img/share-since-2009.png" class="w-[85%] h-auto -mt-5 -ml-5" />
</a>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>




--- #8
transition: fade-out
layout: section
---

# Android 开发环境的搭建

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #9
transition: fade-out
level: 2
---

# 搭建步骤总览


<v-clicks>

1. 安装 JDK：安卓开发需要 Java，所以首先需要安装 JDK。如果使用 Kotlin 开发，尽管是一门独立的语言，同样需要 JDK。
2. 安装 Android Studio：Android 官方推荐的 IDE，提供了丰富的开发工具和模拟器。
3. 配置 Android SDK：根据所需适配的安卓版本，下载相关的 SDK，Android SDK 是 Android 开发的核心工具，包含了 Android 系统的所有 API。
4. 创建 AVD：Android Virtual Device，模拟器，用于在电脑上模拟安卓设备。
5. 创建项目：创建一个新的 Android 项目，选择语言（Java/Kotlin）和模板（Empty Activity/Basic Activity）。
6. 第一个 Hello World：运行项目，查看效果。

</v-clicks>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #10
transition: fade-out
level: 2
---

# 安装 JDK

<div class="relative h-full w-full">
<div class="absolute w-full h-full top-0 left-0">

<v-clicks>

- 安卓开发需要安装 JDK（Java Development Kit）。
- 下载地址：[Oracle JDK](https://www.oracle.com/java/technologies/downloads) 或 [OpenJDK](https://jdk.java.net/)
- 安装完成后，配置环境变量。以 Windows 为例，添加系统环境变量 `JAVA_HOME`，值为 JDK 的安装目录，例如张三的 JDK 安装在 `C:\Program Files\Java\jdk-21`，则 `JAVA_HOME` 的值为 `C:\Program Files\Java\jdk-21`；再在系统环境变量 Path 中添加 `%JAVA_HOME%\bin`，这里的`%JAVA_HOME%`就是刚刚设置的系统环境变量 `JAVA_HOME` 的值。

</v-clicks>

</div>
<div class="absolute w-full h-full top-0 left-0 bg-white" v-click>
<img src="/img/java-home.png" class="w-[78%] h-auto">
</div>

<div class="absolute w-full h-full top-0 left-0 bg-white" v-click>
<img src="/img/path.png" class="w-[78%] h-auto">
</div>

</div>


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 设置换将变量时，用户变量和系统变量都可以，如果是系统变量，那就是给这台电脑所有用户设置的。 -->

--- #11
transition: fade-out
level: 2
---

# 安装 Android Studio

在很早之前，Android 项目都是使用 Eclipse 来开发的，它是 Java 开发神器，安装 ADT（Android Development Tools）插件后就可以用来开发 Android 程序了。而在 2013 年，Google 推出了一款官方的 IDE 工具 Android Studio，由于不再是以插件的形式存在，Android Studio 在开发 Android 程序方面要远比 Eclipse 强大和方便得多。

- 下载地址：[Android Studio](https://developer.android.com/studio)

<img src="/img/android-studio.png" class="w-full h-auto -ml-[20%]">




<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #12
transition: fade-out
level: 2
---

# 配置 Android SDK

<div class="relative h-full w-full">

<div class="absolute top-0 left-0 h-full w-full">

Android SDK 是 Android 开发的核心工具，包含了 Android 系统的所有 API。Android Studio 会自动下载 SDK，但是如果需要适配特定的安卓版本，可以手动下载。Android SDK 包含以下主要组件：

<v-clicks>

- SDK Platform：包含特定版本 Android 系统的 API，用于编译和运行应用程序。
- Sources for Android SDK：包含 Android 系统源代码，用于调试。
- System Images：包含模拟器的系统镜像，用于在模拟器上运行应用程序。
- SDK Tools：包含 Android 开发工具，如 adb（Android Debug Bridge）、emulator（模拟器）、Platform Tools、NDK（Native Development Kit）等。

</v-clicks>

</div>

<div class="absolute top-0 left-0 h-full w-full bg-white z-10" v-click>
  <img src="/img/sdk-platforms.png" class="w-[85%] h-auto">
</div>

<div class="absolute top-0 left-0 h-full w-full bg-white z-20" v-click>
  <img src="/img/sdk-tools.png" class="w-[85%] h-auto">
</div>

<div class="absolute -top-1 left-0 h-full w-full bg-white z-30" v-click>
  <img src="/img/sdk-size.png" class="w-[60%] h-auto">
</div>

</div>

<!-- 
SDK 在安装 Android Studio 时，应该已经安装了（网络好的情况），如果网络状况不佳，可以先跳过 SDK 下载，安装完 Android Studio 后再下载 SDK 并导入。
Platform Tools：包含 adb（Android Debug Bridge）、fastboot 等工具。fastboot 是一个用于刷机的工具，可以用来刷机、解锁 bootloader、刷 recovery 等。
NDK(Native Development Kit)：用于在 Android 应用中使用本地代码（C/C++）。
 -->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #13
layout: two-cols-header
transition: fade-out
level: 2
---

# 创建 AVD

::left::

Android Virtual Device（AVD）是 Android Studio 提供的模拟器，用于在电脑上模拟安卓设备。在 Android Studio 中，可以通过 AVD Manager 创建和管理模拟器。

<v-clicks>

- 打开 Android Studio，点击 `Tools` -> `Devices Manager`。
- 点击加号小图标 `Add a new device`，选择一个设备类型，例如 Pixel 4。
- 选择一个系统镜像，例如 Android 8.0（API 26）。
- 配置 AVD 的参数，例如分辨率、启动时方向、软硬件加速等。
- 点击 `Finish` 完成创建。

</v-clicks>

::right::

<div class="flex flex-col items-center" v-click>
<img src="/img/pixel.png" class="w-[60%] h-auto">
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
模拟器只能模拟软件和部分硬件，模拟器上运行的应用程序可能会和真机上有所不同。模拟器的性能也不如真机。在碰到特定机型的问题或特殊的硬件如 NFC、传感器等时，只能使用真机调试。
 -->

--- #14
transition: fade-out
level: 2
---

# 创建项目

<div class="relative h-full w-full">

<div class="absolute top-0 left-0" v-click.hide>

在 Android Studio 中，可以通过 `File` -> `New` -> `New Project` 创建一个新的 Android 项目。在创建项目时，需要选择项目的语言（Java/Kotlin）和模板（Empty Activity/Basic Activity）。

<v-clicks>

- 模板：Android Studio 提供了一些模板，例如 Empty Activity、Basic Activity、Navigation Drawer Activity、Bottom Navigation Activity 等，可以根据项目需求选择。
- 项目名称：项目名称是 Android 项目的显示名称，例如 `MyApp`。
- 包名：包名是 Android 项目的唯一标识，一般是公司域名的反写，例如 `com.example.myapp`。
- 项目路径：项目路径是 Android 项目的存放路径，可以选择默认路径或自定义路径。
- 语言：Android Studio 支持 Java 和 Kotlin 两种语言，Kotlin 是一种由 JetBrains 开发的现代化编程语言，谷歌宣布 Kotlin 成为 Android 官方开发语言。
- 其他配置：还可以配置项目的最低 SDK 版本、编译配置语言等。

</v-clicks>

</div>

<div class="absolute top-0 left-0" v-click>
<img src="/img/create-project.png" class="w-[70%] h-auto" />
</div>

</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #15
transition: fade-out
level: 2
---

# 第一个 Hello World

<SlidevVideo v-click autoplay controls class="w-[85%] h-auto">
  <!-- Anything that can go in a HTML video element. -->
  <source src="/video/hello-world.mp4" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/video/hello-world.mp4">here</a>.
  </p>
</SlidevVideo>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


--- #16
transition: fade-out
layout: section
---

# Android 项目结构

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #17
transition: fade-out
level: 2
---

# 目录结构总览

````md magic-move
```java
// 根目录结构
.
├── app               // 项目的主模块文件夹
├── build.gradle      // 项目级别的 build.gradle，用于配置整个项目的构建设置和依赖项
├── .gitignore        // Git 忽略文件
├── .gradle           // Gradle 缓存目录，用于存储与构建相关的缓存文件和临时文件
├── gradle            // Gradle 目录
├── gradle.properties // 用于配置 Gradle 构建系统的全局属性，可以调整构建构成的行为和性能
├── gradlew           // 脚本文件，用于 Unix 系统（如 Linux 和 macOS）上执行 Gradle 的构建命令
├── gradlew.bat       // 脚本文件，用于 Windows 系统上执行 Gradle 的构建命令
├── local.properties  // 本地配置文件，主要是 SDK 路径
└── settings.gradle   // 定义项目包含的所有模块
```
```java
// 展开 app 文件夹
./app
├── build.gradle                              // 模块级别的 build.gradle，用于配置模块的构建设置和依赖项
├── .gitignore                                // Git 忽略文件
├── proguard-rules.pro                        // ProGuard 规则文件，用于代码混淆和优化
└── src                                       // 源代码目录
    ├── androidTest                           // Android 测试代码
    ├── main                                  // 主代码目录
    │   ├── AndroidManifest.xml               // Android 应用的清单文件
    │   ├── java                              // Java 源代码 
    │   │   └── com                           // 包名
    │   │       └── example                   // 项目名
    │   │           └── projectstructure      // 模块名
    │   │               └── MainActivity.java // 应用的主要活动类文件
    │   └── res                               // 资源目录
    └── test                                  // 单元测试代码
...
```

```java
res // 展开 app/src/main/res 文件夹
├── drawable                                  // 存放图片资源
│   ├── ic_launcher_background.xml            // 应用图标背景
│   └── ic_launcher_foreground.xml            // 应用图标前景
├── layout                                    // 存放布局文件
│   └── activity_main.xml                     // 主活动的布局文件
├── mipmap-anydpi                             // 存放应用图标（适配所有分辨率）
│   ├── ic_launcher_round.xml                 // 圆形图标
│   └── ic_launcher.xml                       // 正方形图标
├── mipmap-hdpi                               // 存放应用图标（高分辨率），240dpi
│   ├── ic_launcher_round.webp                // 圆形图标
│   └── ic_launcher.webp                      // 正方形图标
├── mipmap-mdpi                               // 存放应用图标（中分辨率），160dpi
├── mipmap-xhdpi                              // 存放应用图标（超高分辨率），320dpi
├── mipmap-xxhdpi                             // 存放应用图标（超超高分辨率），480dpi
├── mipmap-xxxhdpi                            // 存放应用图标（超超超高分辨率），640dpi
├── values                                    // 存放资源文件
│   ├── colors.xml                            // 颜色资源
│   ├── strings.xml                           // 字符串资源
│   └── themes.xml                            // 主题资源
├── values-night                              // 夜间模式资源
│   └── themes.xml                            // 夜间模式主题资源
└── xml                                       // 存放 XML 文件
    ├── backup_rules.xml                      // 备份规则
    └── data_extraction_rules.xml             // 数据提取规则
```
````

<!-- 
anydpi 是分辨率为任意的，这里存放的是适配所有分辨率的图标，例如圆形图标和正方形图标。
hdpi 是分辨率为 240dpi 的，这里存放的是高分辨率的图标。
mdpi 是分辨率为 160dpi 的，这里存放的中分辨率的图标。
xhdpi 是分辨率为 320dpi 的，这里存放的是超高分辨率的图标。
xxhdpi 是分辨率为 480dpi 的，这里存放的是超超高分辨率的图标。
xxxhdpi 是分辨率为 640dpi 的，这里存放的是超超超高分辨率的图标。

如果需要国际化，默认语言包存放在 values 文件夹下，values-zh 存放中文简体语言包，values-en 存放英文语言包。
 -->

--- #18
transition: fade-out
level: 2
---

# AndroidManifest.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"                              <!-- 应用图标 -->
        android:label="@string/app_name"                                <!-- 应用名称 -->
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.ProjectStructure"
        tools:targetApi="31">
        <!-- 申明一个 Activity -->
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
AndroidManifest.xml 用于描述应用的基本信息，如应用名称、图标、权限、组件等。在 AndroidManifest.xml 中，可以声明应用的 Activity、Service、BroadcastReceiver、ContentProvider 等组件，以及权限、权限组、应用的配置信息等。

也可以看成路由注册表，当应用启动时，系统会根据 AndroidManifest.xml 中的配置信息来启动相应的组件。
 -->

--- #19
transition: fade-out
level: 2
---

# 项目级别的 build.gradle

Android Studio 是采用 Gradle 来构建项目的。Gradle 是一个非常先进的项目构建工具，它使用了一种基于 Groovy 的领域特定语言 DSL（ Domain Specific Language）来进行项目设置，摒弃了传统基于 XML（如 Ant 和 Maven）的各种烦琐配置。

<v-click>

```groovy
// Top-level build file where you can add configuration options common to all sub-projects/modules.
plugins {
// 默认的 Android 插件被放置在这里，不会立即应用（apply false）。这样做的目的是在模块级别的 build.gradle 文件中更灵活的应用这些插件。
alias(libs.plugins.android.application) apply false 
}
```

</v-click>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
在新版本的 Android Studio 中，项目级别的 build.gradle 文件中只包含了一个 `plugins` 块，用于禁用默认的 Android 插件。项目级别的 build.gradle 文件用于配置整个项目的构建设置和依赖项。 

这意味着在子模块中，可以自由选择是否应用 Android 插件，这样可以更灵活的控制项目的构建行为。

同时因为根 build.gradle 文件中固定了插件的版本号，简化了插件版本的管理，确保所有的模块使用相同的插件版本，避免版本冲突。

根目录中的 build.gradle 由 Android Studio 自动生成，一般情况下不需要修改，除非需要增加一些全局的配置。
-->

--- #20
transition: fade-out
level: 2
---

# 模块级别的 build.gradle


````md magic-move
```groovy
plugins {         // 定义模块中使用的插件
  // ...
}
android {         // 定义 Android 构建设置
  // ...
}
dependencies {    // 定义模块的依赖项
  // ...
}
```
```groovy
plugins {
    alias(libs.plugins.android.application) // 应用 Android 插件
    // alias(libs.plugins.jetbrains.kotlin.android) // 应用 Kotlin 插件
}
android {
 // ...
}
dependencies {
  // ...
}
```
```groovy
plugins {// ...
}
android {
    namespace 'com.example.projectstructure'            // 包名
    compileSdk 34                                       // 编译 SDK 版本
    defaultConfig {                                           
        applicationId "com.example.projectstructure"    // 应用 ID
        minSdk 26
        targetSdk 34
        versionCode 1                                   // 版本号
        versionName "1.0"                               // 版本名称
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner" // 测试运行器
    }
    buildTypes {
        release {
            minifyEnabled false                          // 是否启用代码混淆
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8      // 源代码兼容性
        targetCompatibility JavaVersion.VERSION_1_8      // 目标兼容性
    }
}
dependencies {// ...
}
```
```groovy
plugins {
    // ...
}
android {
    //...
}
dependencies {
    implementation libs.appcompat                 // AppCompat 库
    implementation libs.material                  // Material Design 库
    implementation libs.activity                  // Activity 库
    implementation libs.constraintlayout          // 约束布局库
    testImplementation libs.junit                 // JUnit 测试库
    androidTestImplementation libs.ext.junit      // Android JUnit 测试库
    androidTestImplementation libs.espresso.core  // Espresso 测试库
}
```
````

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
首先第一行应用了一个插件，一般有两种值可选：com.android.application 表示这是一个应用程序模块，com.android.library 表示这是一个库模块。二者最大的区别在于，应用程序模块是可以直接运行的，库模块只能作为代码库依附于别的应用程序模块来运行。

如果想要使用 Kotlin 来开发 Android 项目，就需要使用 libs.plugins.jetbrains.kotlin.android 这个插件

 -->

--- #21
transition: fade-out
level: 2
---

# values 文件夹

<v-click>

```xml
// colors.xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color> <!-- 布局文件中通过 @color/black 引用 -->
    <color name="white">#FFFFFFFF</color> <!-- Java/Kotlin 代码中通过 R.color.white 引用 -->
</resources>
```

</v-click>

<v-click>

```xml
// strings.xml
<resources>
    <string name="app_name">Project Structure</string> <!-- 布局文件中通过 @string/app_name 引用 -->
</resources>
```

</v-click>

<v-click>

```xml
// themes.xml
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- 基础主题，继承自 Material3 主题 -->
    <style name="Base.Theme.ProjectStructure" parent="Theme.Material3.DayNight.NoActionBar">
        <!-- Customize your light theme here. -->
        <!-- <item name="colorPrimary">@color/my_light_primary</item> -->
    </style>
    <!-- 应用主题，在 AndroidManifest.xml 中，可以通过 android:theme="@style/Theme.ProjectStructure" 来应用自定义主题 -->
    <style name="Theme.ProjectStructure" parent="Base.Theme.ProjectStructure" />               <!-- 应用主题 -->
</resources>
```

</v-click>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
themes.xml 中并非有两个主题，Base.Theme.ProjectStructure 是基 theme，Theme.ProjectStructure 是自定义 theme，继承了 Base.Theme.ProjectStructure。

这种结构可以使得在 Base 中定义通用样式，然后在需要时通过继承来进行具体的应用样式自定义。这样的方法提供了灵活性和可维护性，因为你可以在一个地方定义通用样式，而不必在每一个具体的主题中重复定义
 -->

--- #22
transition: fade-out
layout: section
---

# 看得见的 Activity

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #23
layout: two-cols-header
transition: fade-out
level: 2
---

# 什么是 Activity？

::left::

Activity 是 Android 应用的一个组件，它提供了一个用户界面，用户可以与之交互。Activity 通常是一个单独的屏幕，它可以包含一些 UI 控件，如按钮、文本框、列表等。

<v-clicks>

- 一个应用可以包含多个 Activity，每个 Activity 都是一个单独的屏幕。
- 每个 Activity 都可以调用其他 Activity，实现页面之间的跳转。
- Activity 也可以调用其他应用的 Activity，实现应用之间的跳转。
- Activity 有生命周期，包括创建、启动、暂停、恢复、停止、销毁等状态。

</v-clicks>

::right::

<v-click>

<div class="flex flex-row items-center">
<img src="/img/activity.png" class="w-full h-auto" />
</div>

</v-click>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
例如，淘宝的主 activity 是首页，用户可以通过点击商品进入商品详情页，这个商品详情页就是另一个 activity。
-->

--- #24
transition: fade-out
level: 2
---

# 手动创建 Activity


<SlidevVideo v-click autoplay controls class="w-[80%] h-auto">
  <!-- Anything that can go in a HTML video element. -->
  <source src="/video/create-activity.mp4" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/video/create-activity.mp4">here</a>.
  </p>
</SlidevVideo>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #25
transition: fade-out
level: 2
---

# 详解 FirstActivity

```java
package com.example.projectstructure;

import android.os.Bundle;
import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;
// AppCompatActivity 是 AndroidX 库中的一个 Activity 类，提供了向后兼容的功能
// 继承链：FirstActivity -> AppCompatActivity -> FragmentActivity -> ComponentActivity -> Activity -> ContextThemeWrapper -> ContextWrapper -> Context
public class FirstActivity extends AppCompatActivity {
    // onCreate 方法是 Activity 的生命周期方法，当 Activity 创建时会调用这个方法
    @Override
    protected void onCreate(Bundle savedInstanceState) { // Bundle 是一个键值对的数据结构，用于保存 Activity 的状态
        super.onCreate(savedInstanceState);       // 调用父类的 onCreate 方法
        EdgeToEdge.enable(this);                  // 启用边缘到边缘布局
        setContentView(R.layout.activity_first);  // 设置 Activity 的布局文件为 activity_first.xml，R 是资源文件的引用
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
}
```

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


<!-- 
希望在较老的 Android 设备中使用一些较新的平台特性的 Activity 的基类。

之前 Java 中构造函数使用 super 完成初始化。在继承中，Override 一个方法时，如果想要调用父类的方法，可以使用 super 关键字，来继续添加一些新的逻辑。 如果在 Override 中不调用 super.onCreate()，则是对该方法的完全重写，会导致父类的方法不会被调用。在这里会影响到父类的初始化逻辑，导致一些意外的行为。

ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {...}): 为布局中的 main 视图设置一个窗口插入事件监听器。当系统窗口（如状态栏和导航栏）发生变化时，会调用这个监听器。这里使用 lambda 表达式来实现监听器，lambda 表达式是一种简洁的语法，用于创建匿名函数。
Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());: 从 WindowInsetsCompat 对象中获取系统栏的插入（insets），这些插入值代表系统栏的大小。
v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);: 为 main 视图设置相应的填充（padding），以确保视图内容不会被系统栏遮挡。
return insets;: 返回 insets 对象，以便继续处理其他插入事件。

这个是为了保证视图内容不被遮挡，提供良好的用户体验。
-->

--- #26
transition: fade-out
level: 2
---

# Activity 中监听点击事件

<div class="relative h-full w-full">
<div class="flex flex-row">

<div class="w-1/2">
```java
// MainActivity.java
package com.example.projectstructure;

import android.os.Bundle;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button1 = findViewById(R.id.button1);
        button1.setOnClickListener((view) -> {
            Toast.makeText(this, "You clicked Button 1", Toast.LENGTH_SHORT).show();
            new Handler().postDelayed(this::finish, 3000);
        });
    }
}
```

</div>


<div class="w-1/2">
```java
// main_activity.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <Button
        android:id="@+id/button1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button 1" />
</LinearLayout>
```

</div>
</div>
<v-click>
<div class="absolute top-0 left-0 bg-white h-full w-full">
<SlidevVideo v-click autoplay controls class="w-[80%] h-auto">
  <!-- Anything that can go in a HTML video element. -->
  <source src="/video/on-click.mp4" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/video/on-click.mp4">here</a>.
  </p>
</SlidevVideo>
</div>
</v-click>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
.show() 不是链式调用，而是一个静态方法，用于创建一个 Toast 对象并显示出来。

this::finish 是 Java8 中引入的方法引用语法的一部分，用于引用当前实例（this）的 finish 方法。方法引用提供了一种简洁的写法，而不需要显示的声明一个 lambda 表达式。
 -->

--- #27
transition: fade-out
level: 2
---

# Activity 之间的跳转

<div class="relative h-full w-full">
<div class="absolute top-0 left-0">

Intent 是 Android 程序中各组件之间进行交互的一种重要方式，它不仅可以指明当前组件想要执行的动作，还可以在不同组件之间传递数据。Intent 一般可用于启动 Activity、启动 Service 以及发送广播等场景。

````md magic-move
```java
// MainActivity.java
package com.example.projectstructure;
import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button1 = findViewById(R.id.button1);
        button1.setOnClickListener((view) -> {
            Intent intent = new Intent(this, FirstActivity.class);
            startActivity(intent);
        });
    }
}
```
```java
// MainActivity.java
package com.example.projectstructure;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button1 = findViewById(R.id.button1);
        button1.setOnClickListener((view) -> {
            Intent intent = new Intent(Intent.ACTION_VIEW);
            intent.setData(Uri.parse("https://baidu.com/"));
            startActivity(intent);
        });
    }
}
```
````

</div>

<div class="absolute h-full w-full bg-white top-0 left-0" v-click>
<SlidevVideo v-click autoplay controls class="w-[80%] h-auto">
  <!-- Anything that can go in a HTML video element. -->
  <source src="/video/baidu.mp4" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/video/baidu.mp4">here</a>.
  </p>
</SlidevVideo>
</div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
显示 Intent 是一个显示的 Intent，用于启动一个指定的 Activity。在这里，我们通过 Intent 的构造方法指定了要启动的 Activity 的类名，然后调用 startActivity 方法来启动这个 Activity。因为意图非常明显，所以这种 Intent 称为显示 Intent。

使用隐式Intent，不仅可以启动自己程序内的Activity，还可以启动其他程序的Activity，这就使多个应用程序之间的功能共享成为了可能。比如你的应用程序中需要展示一个网页，这时你没有必要自己去实现一个浏览器（事实上也不太可能），只需要调用系统的浏览器来打开这个网页就行了。

除了展示网页，隐式Intent 还可以用于打开系统的其他应用程序，比如打开系统的短信应用、电话应用、地图应用等。
 -->

--- #28
transition: fade-out
level: 2
---

# Activity 之间的数据传递

````md magic-move
```java
// 向下传递数据
// MainActivity.java
package com.example.projectstructure;
import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button1 = findViewById(R.id.button1);
        button1.setOnClickListener((view) -> {
            Intent intent = new Intent(this, FirstActivity.class);
            intent.putExtra("key", "value");
            startActivity(intent);
        });
    }
}
```
```java
// FirstActivity.java
package com.example.projectstructure;
import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class FirstActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_first);
        TextView textView = findViewById(R.id.textView);
        String value = getIntent().getStringExtra("key");
        textView.setText(value);
    }
}
```
```java
// 向上传递数据
// MainActivity.java
package com.example.projectstructure;
import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button1 = findViewById(R.id.button1);
        button1.setOnClickListener((view) -> {
            Intent intent = new Intent(this, FirstActivity.class);
            startActivityForResult(intent, 1);
        });
    }
}
```
```java
// FirstActivity.java
package com.example.projectstructure;
import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class FirstActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_first);
        Button button = findViewById(R.id.button);
        button.setOnClickListener((view) -> {
            Intent intent = new Intent();
            intent.putExtra("key", "value");
            setResult(1, intent);
            finish();
        });
    }
}
```
````

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

--- #29
layout: two-cols-header
transition: fade-out
level: 2
---

# Activity 的生命周期

::left::
<img src="/img/lifecycle.png" class="w-[78%] h-auto" />

::right::

<v-clicks>

- onCreate：Activity 创建时调用
- onStart：Activity 可见时调用
- onResume：Activity 可交互时调用
- onPause：Activity 失去焦点时调用
- onStop：Activity 不可见时调用
- onDestroy：Activity 销毁时调用

</v-clicks>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!-- 
当用户浏览、退出和返回到您的应用时，您应用中的 Activity 实例会在其生命周期的不同状态间转换。Activity 类提供了许多回调，这些回调会让 activity 知道状态何时发生变化，或者系统正在创建、停止、恢复 activity 或销毁 activity 所在的进程。

在生命周期回调方法中，您可以声明用户离开和再次进入 Activity 时 Activity 的行为方式。例如，如果您构建的是流式视频播放器，当用户切换到其他应用时，您可以暂停视频并终止网络连接。当用户返回时，您可以重新连接到网络，让用户从同一位置继续播放视频。
 -->

--- #30
layout: end
transition: fade-out
---

# 谢谢观看😃

该幻灯片可以在👉[android-tutorial.vercel.app](https://android-tutorial.vercel.app)上查看
