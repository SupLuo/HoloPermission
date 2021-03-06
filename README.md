[![Release](https://img.shields.io/badge/release-1.0.5--rc-blue.svg)](https://github.com/SupLuo/HaloPermission/releases)
[![GitHub license](https://img.shields.io/github/license/SupLuo/HaloPermission.svg)](https://github.com/SupLuo/HaloPermission/blob/master/LICENSE.txt)

## HoloPermission
An Android permission library developed by Kotlin language with higher extensibility and compatibility.

Kotlin语言开发的具有高可扩展性和可控性的Android权限库。

### Features   
* 良好的设计和可扩展性（个人觉得最区别于别的库的最主要原因）
* 兼容到8.0所需要的相关特殊权限，并可以很好的进行扩展（未知来源、悬浮窗、系统设置修改、通知、通知渠道等权限的处理）
* 支持RationaleRender（向用户解释为什么申请权限）
* 支持SettingRender（当权限没有授权时，可以打开权限设置界面进行设置，并自动检测设置是否改变）
* 更好的系统权限设置界面兼容性（尽量兼容不同的系统厂商的权限设置界面）
* 6.0以下权限支持（不建议，感觉没必要了）


## [HaloPermission解惑(Why choose "HaloPermission")](https://github.com/SupLuo/HaloPermission/blob/master/doc/What%20is%20%22HaloPermission%22.md)
您可能对HaloPermission有诸多疑问：已经有那么多成熟的权限处理框架，为什么要用这个？这个有什么值得使用的理由？为什么这个库的星星这么少？这库到底靠谱不靠谱？...
希望[HaloPermission解惑](https://github.com/SupLuo/HaloPermission/blob/master/doc/What%20is%20%22HaloPermission%22.md)能够消除您心中的疑虑。


### Setup

在使用HaloPermission的Module的build.gradle中添加以下依赖：
```
    dependencies {
        //gradle 3.+以后不是使用'compile'方法，而是使用'implementation' or 'api'等方式
        compile('halo.android:permission:1.0.5-rc@aar'){
            //传递依赖
            transitive = true
        }
    }

```

额外配置说明:

1. V7依赖说明

    HaloPermission依赖`com.android.support:appcompat-v7:28.0.0`包（本身也依赖v4包，但v7依赖v4，所以引入v7即可），如果与您工程依赖的版本不一致，你可以排除HaloPermission的版本依赖。
        但是`appcompat-v7`的版本不能低于24.1.+

    ```
        compile('halo.android:permission:1.0.5-rc@aar'){
            //传递依赖
            transitive = true
            //排除appcompat-v7依赖
            exclude group: 'com.android.support', module: 'appcompat-v7'
        }
    ```

2. Kotlin依赖说明（项目不支持Kotlin开发的童鞋可以忽略）

    HaloPermission是基于`org.jetbrains.kotlin:kotlin-stdlib:1.3.11`开发的，如果您的工程也支持Kotlin开发，并且与HaloPermission版本不一致，您可以排除HaloPermission对`kotlin-stdlib`的依赖。
    但是`kotlin-stdlib`的版本最好不能低于1.3.11
    ```
        compile('halo.android:permission:1.0.5-rc@aar'){
            //传递依赖
            transitive = true
            //排除kotlin-stdlib依赖
            exclude group: 'org.jetbrains.kotlin', module: 'kotlin-stdlib'
        }
    ```

### Usage
**[查看详细使用](https://github.com/SupLuo/HoloPermission/blob/master/doc/README_USAGE.md)**

### 运行效果图
直接下载demo运行吧。。。
[Demo下载地址](https://github.com/SupLuo/HaloPermission/blob/master/doc/app-release.apk)

### 缺陷说明
对于6.0以下的权限处理，某些权限校验**可能**并不准确，这一部分稍后进一步说明原因。
不仅HaloPermission如此，大多数有名的框架也不能解决这些问题。但是这并不影响app的正常逻辑流程，因为在后续流程中你能够得到更具体的一些信息。

### 联系方式
QQ：862638161

Email:super_luo@163.com

如需交流，欢迎讨论
