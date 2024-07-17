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


--- #15
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

--- #16
transition: fade-out
level: 2
---

# 项目结构总览

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
├── mipmap-anydpi                             // 
│   ├── ic_launcher_round.xml
│   └── ic_launcher.xml
├── mipmap-hdpi
│   ├── ic_launcher_round.webp
│   └── ic_launcher.webp
├── mipmap-mdpi
├── mipmap-xhdpi
├── mipmap-xxhdpi
├── mipmap-xxxhdpi
├── values
│   ├── colors.xml
│   ├── strings.xml
│   └── themes.xml
├── values-night
│   └── themes.xml
└── xml
    ├── backup_rules.xml
    └── data_extraction_rules.xml
```
````






