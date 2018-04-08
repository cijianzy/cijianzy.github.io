---
title: Swift2OC
date: 2018-04-03 16:55:12
tags: Swift
---
### 起因 
最近因为项目需求，需要将原有的一些Swift代码转换成OC代码，因为工作毫无挑战性，所以想写一个Swift to Objective-C 的工具来做一些沉淀

### 设计
目前暂时的设计是这样的

![image](https://raw.githubusercontent.com/cijianzy/img.cijianzy.github.com/master/Swift2OC/Swift2OC_Flow.PNG)

发现苹果Swift也有 Class/Function definition 级别的工具（就是产生Module-Swift.h）,可以借鉴看下

[PrintAsObjC](https://github.com/apple/swift/blob/master/lib/PrintAsObjC/PrintAsObjC.cpp)

### 代码仓库
目前代码仓库在这里: [代码仓库][GitHub Pages]


[GitHub Pages]: https://github.com/cijianzy/Swift2OC

