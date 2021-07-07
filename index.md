---
sidebarDepth: 2
---
# 什么是Monibuca？

**Monibuca** 是一个开源的流媒体服务器开发框架，适用于快速定制化开发流媒体服务器，可以对接 `CDN` 厂商，作为回源服务器，也可以自己搭建集群部署环境。
内置了后台 `web` 界面，方便观察服务器运行的状态。
也可以自己开发后台管理界面，通过 `api` 方式获取服务器的运行信息。
**Monibuca** 提供了可供定制化开发的插件机制，可以任意扩展其功能。

核心引擎以及内置插件提供的功能：
- 协议互相转换，音视频流转发
- 接收RTMP协议推流、RTMP协议拉流播放
- 接收RTSP协议推流、从远程拉取RTSP流
- 读取远程HLS流、生成HLS流
- 录制FLV格式文件、读取FLV格式流、读取TS文件流
- GB28181协议支持
- HTTP-FLV、WS-FLV、WS-RAW格式拉流播放
- 集群功能
- 接收WebRTC推流、WebRTC拉流播放

## 流媒体服务器项目有很多，为什么要重复发明轮子？
**Monibuca** 不同于其他流媒体服务器的地方是，针对二次开发为目的。多数流媒体服务器，对于二次开发并不友好。 **Monibuca** 开创了插件机制，可以自由组合不同的协议或者功能，定制化特定需求的流媒体服务器。

## Monibuca为何采用Golang为开发语言？
因为 `Golang` 语言相比其他语言可读性更强，代码简单易懂，更利于二次开发；另外 `Golang` 的 `goroutine` 特别适合开发高速系统。

## Monibuca是否使用Cgo或者其他语言依赖库？
没有。 **Monibuca** 是纯 `Go` 语言开发，不依赖任何其他第三方库比如 `FFmpeg` ，方便二次开发。对部署更友好，仅仅需要 `Golang` 运行环境即可。

## Monibuca对环境有什么要求？直播流可以在微信里播放吗？
**Monibuca** 是基于 `Golang` 开发，支持跨平台部署。 **Monibuca** 可以用 `Jessibuca` 播放器在微信、手机浏览器里面播放视频。也可以通过其他 `SDK` 播放 `RTMP` 流、其他协议的流。只需要相应的插件支持即可。

## Jessibuca是什么？
`Jessibuca` 是一款使用 `Emscripten` 编译的纯 `H5` 播放器，支持 `H264` 、 `H265` 格式的直播流，[已开源]（http://jessibuca.monibuca.com）

## Monibuca的名称有什么特殊含义吗？
这个单词来源于 `Monica` （莫妮卡）是个人名，在项目里面也存在这个文件夹。没有特别含义，为了解决起名的难题，使用了三个名称分别是 `Monica` 、 `Jessica` 、`Rebecca` 用来代表服务器、播放器、推流器。由于莫妮卡、杰西卡、瑞贝卡，都带卡字，对直播来说寓意不好，所以改为莫妮不卡（`Monibuca`）、杰西不卡[Jessibuca](http://jessibuca.monibuca.com)、瑞贝不卡（`Rebebuca`）。其中推流器 `Rebebuca` 目前尚为公布，是改造了的 `OBS` ，可用于推流 `H265` 。