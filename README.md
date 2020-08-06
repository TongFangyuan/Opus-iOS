# Opus-iOS

> Opus是一个完全开放、免版税、高度通用的音频编解码器。Opus在互联网上的交互式语音和音乐传输方面是无可比拟的，但也适用于存储和流媒体应用。它被互联网工程任务组(IETF)标准化为RFC 6716，其中融合了Skype的SILK编解码器和Xiph.Org的CELT编解码器的技术。

编译 [Opus Codec](http://www.opus-codec.org) iOS 脚本

## 编译步骤

1. (Objective-C) [编译静态库](#编译静态库)
2. (Optionally for Swift) [编译 framework ](#framework)

## 编译静态库

#### Step 1

运行命令行代码：

```bash
$ ./build-libopus.sh
```

将会下载源码压缩包倒`build/src`目录下，并将编译好的静态库将会放在`dependencies`目录下。

**Note** 如果官网有[最新的稳定版tar文件](http://opus-codec.org/downloads/)，记得及时更新 `build-libopus.sh`文件对应的版本号。

#### Step 2

按照上面的步骤，从静态库中构建框架


## framework

#### Step 1

打开 `opus/opus.xcodeproj` 文件, 选择 `UniversalTarget` 和 `Generic iOS Device`

#### Step 2

运行工程，生成`opus.framework`, 文件路径在根目录下。

**Note** 生成的framework适用于模拟器和真机。



#### Step 3

验证生成的`framework`是否支持真机和模拟器 (x86_64 i386 armv7 armv7s arm64)

```bash
$ lipo -info opus.framework/opus
```

## License

MIT
