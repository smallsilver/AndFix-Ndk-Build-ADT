# AndFix-Ndk-Build-ADT
AndFix热更新源码的编译项目 


## 说明
> **如果项目只包含了 armeabi，那么在所有Android设备都可以运行； 如果项目只包含了 armeabi-v7a，除armeabi架构的设备外都可以运行； 如果项目只包含了 x86，那么armeabi架构和armeabi-v7a的Android设备是无法运行的； 如果同时包含了 armeabi， armeabi-v7a和x86，所有设备都可以运行，程序在运行的时候去加载不同平台对应的so，这是较为完美的一种解决方案，同时也会导致包变大。**

以上引用的原文链接：[http://www.it165.net/embed/html/201410/2707.html](http://www.it165.net/embed/html/201410/2707.html) 

## 项目背景
阿里巴巴的[AndFix](https://github.com/alibaba/AndFix "AndFix")热更新开源项目默认生成armeabi以及x86的so库文件。

如果apk中有对应平台的文件夹，但是文件夹里却没有对应的so。

举个栗子，apk中lib下面一旦出现arm64-v8a文件夹，程序运行的时候就会去加载arm64-v8a对应的库，但是如果此时arm64-v8a文件夹没有将so放进来，则会遇到报错。

## 项目目的
为了进可能地兼容AndFix的使用稳定性，这个项目引入了AndFix的源码，对apk的lib的所有平台进行编译成所对应的so库文件。

## 使用
下载项目，找到lib下目录，复制除了armabi和x86的目录到你的项目当中即可。
你可以进行二次编译～～