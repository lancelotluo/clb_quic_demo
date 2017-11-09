CLB quic demo
===================================

Quic是一种非常先进同时也在快速普及的协议，它能够大幅提升WEB页面的性能（15%以上）。腾讯云CLB（cloud load balance）目前已经在服务端支持了Quic协议，Demo中的图片由腾讯云CLB接入的网站提供。  
不过目前支持Quic的客户端比较少，这个Demo主要是告诉大家如何在客户端使用Quic协议。  
Demo使用了[Cronet](https://chromium.googlesource.com/chromium/src/+/master/components/cronet?autodive=0%2F%2F)
，Google Chromium的开源网络库，同时在Cronet Sample的基础上简单修改，遵循Apache2.0开源许可证发布。

### 如何使用
---------------
1. git clone下载之后直接使用android studio打开即可编译和运行。
2. 如果需要翻墙，请修改gradle.properties文件，添加相应的代理。

### 如何更新Cronet
当前版本默认使用了63.0.3203，如果需要更新Cronet，按照如下步骤：

1. 访问Cronet网站。https://console.cloud.google.com/storage/browser/chromium-cronet/android,选择对应的版本。
2. 找到对应版本号的目录 chromium-cronet/android/{版本号}/Release/cronet。
3. 下载cronetapi.jar, cronetimplcommonjava.jar cronetimplnative_java.jar三个jar文件。
4. 将上述三个jar文件更新到 app/libs下。
5. 如果文件名或者版本号有变化，需要更新app/build.gradle文件中相应的库文件名。没有变化则忽略。
6. 进入chromium-cronet/android/{版本号}/Release/cronet/libs目录，下载so文件，包括两个目录：armeabi 和 armeabi-v7a。如果需要使用PC端的模拟器，需要下载x86_64目录。
7. 将下载好的armeabi和armeabi-v7a,x86_64拷贝至app/src/main/jniLibs目录。
8. 更新完成。


### License
---------------

```
Copyright 2015 Google, Inc.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements. See the NOTICE file distributed with this work for
additional information regarding copyright ownership. The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
