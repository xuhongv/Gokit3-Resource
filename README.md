<p align="center">
  <img src="https://github.com/xuhongv/Gokit3-Resource/blob/master/Pic/g3-bg.png" width="1100px" height="500px" alt="Banner" />
</p>


[Github项目主页](https://github.com/xuhongv/Gokit3-Resource)
 
 
# 一、目录

- [概要](#概要)
- [changelog](#changelog)
- [目录结构及文件含义](#目录结构及文件含义)
- [功能模块文档](#功能模块文档)
- [米家扩展程序示例代码](#米家扩展程序示例代码)
- [开发新的米家扩展程序](#开发新的米家扩展程序)
- [测试米家扩展程序](#测试米家扩展程序)
- [上传米家扩展程序](#上传米家扩展程序)
- [开发注意事项](#开发注意事项)
- [开发遇到的问题](#开发遇到的问题)

# 二、概要

   Gokit3-Resource是为已接入米家APP的智能设备提供的米家扩展程序Android开发环境，里面包含米家APP提供给扩展程序的各种功能API，以及常用的UI组件。米家扩展程序也是基于Android环境开发的，开发扩展程序的时候请确保Android配置信息（比如compileSdkVersion、minSdkVersion、targetSdkVersion）与米家最新版本保持一致。
   
   
# 目录结构及文件含义

* gen_plug.py
	* 自动生成米家扩展程序工程脚本
* MiJiaAuthSDK
	* 提供米家Auth授权SDK
* mibtservice
	* 当设备运行的是Android系统的时候，此SDK给设备提供米家标准蓝牙通信协议，并且封装RPC、获取米家APP设备属性等功能
* common_ui
	* 封装了一些通用的米家UI组件，米家扩展程序可以使用(扩展程序工程可通过plug.gradle脚本添加引用，不需要直接引用)
* libs_ex
	* 提供了一些通用的第三方sdk，比如appcompat-v7、support-v4、support-v13、recyclerview、微信sdk等，米家扩展程序开发的时候不需要在自己的工程中重复引用这些第三方sdk(扩展程序工程可通过plug.gradle脚本添加引用，不需要直接引用)
* pluglib
	* 封装了米家APP提供给扩展程序的各种api(扩展程序工程可通过plug.gradle脚本添加引用，不需要直接引用) 
* plugProject
	* 提供了一些Demo工程，米家扩展程序开发的时候可以参考
	* 第三方自己开发的米家扩展程序工程也可以放置在此目录下
* plug.gradle
	* 封装了common\_ui、libs\_ex、pluglib工程的引用，米家扩展程序只需要在自己的build.gradle脚本中添加`apply from: "${project.rootDir.absolutePath}/plug.gradle"`就可以自动依赖了
	* 米家扩展程序的调试安装也是在该脚本实现
* SmartHome.apk
	* 米家扩展程序开发调试的时候请使用此调试apk，不要使用线上版本的米家APP，另外调试的时候务必关闭应用商店的自动升级功能，避免调试apk被覆盖
* md_image
	* 存放SDK使用文档中引用到的图片，米家扩展程序开发可忽略
