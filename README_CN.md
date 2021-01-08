[English](https://github.com/cmdbug/YOLOv5_NCNN/blob/master/README.md)

## :rocket: 如果有帮助，点个star！:star: ##

### 移动端NCNN部署，项目支持YOLOv5s、YOLOv4-tiny、MobileNetV2-YOLOv3-nano、Simple-Pose、Yolact、ChineseOCR-lite、ENet、Landmark106、DBFace、MBNv2-FCN与MBNv3-Seg-small模型，摄像头实时捕获视频流进行检测。

## iOS:
- Xcode 11.5
- macOS 10.15.4
- iPhone 6sp 13.5.1

## Android:
- Android Studio 4.0
- Win10 1909
- Meizu 16x 8.1.0 (CPU:Qualcomm 710 GPU:Adreno 616)

安卓已经增加权限申请，但如果还是闪退请手动确认下相关权限是否允许。

android studio编译出现ndk版本问题
```code
在app/build.gradle文件中ndk配置项前添加：ndkVersion '本地安装的ndk相应版本号'
```
> iOS
```code
从界面中选择需要测试的模型。
```
> Android
```
从界面中选择需要测试的模型。
```
### 模型
| model | android | iOS | from |
|-------------------|:--------:|:--------:|:--------:|
| YOLOv5s           | yes | yes |  [Github](https://github.com/ultralytics/yolov5)   |
| YOLOv4-tiny       | yes | yes |  [Github](https://github.com/ultralytics/yolov3)   |
| YOLOv3-nano       | yes | yes |  [Github](https://github.com/dog-qiuqiu/MobileNet-Yolo)   |
| YOLOv5s_custom_op | yes | yes |  [zhihu](https://zhuanlan.zhihu.com/p/275989233)   |
| NanoDet           | yes | yes |  [Github](https://github.com/RangiLyu/nanodet)   |
| YOLO-Fastest-xl   | yes | bug |  [Github](https://github.com/dog-qiuqiu/Yolo-Fastest)   |
| Simple-Pose       | yes | yes |  [Github](https://github.com/dog-qiuqiu/MobileNet-Yolo)   |
| Yolact            | yes | yes |  [Github](https://github.com/dbolya/yolact) [zhihu](https://zhuanlan.zhihu.com/p/128974102)  |
| ChineseOCR_lite   | yes | cancel |  [Github](https://github.com/ouyanghuiyu/chineseocr_lite) [zhihu](https://zhuanlan.zhihu.com/p/113338890)   |
| ENet              | bug | cancel |  [Github](https://github.com/davidtvs/PyTorch-ENet)   |
| Landmark106       | yes | yes |  [Github](https://github.com/dog-qiuqiu/MobileNet-Yolo)   |
| DBFace            | yes | yes |  [Github](https://github.com/yuanluw/DBface_ncnn_demo)   |
| MBNv2-FCN         | yes | yes |  [Github](https://github.com/open-mmlab/mmsegmentation)   |
| MBNv3-Seg-small   | yes | yes |  [Github](https://github.com/Tramac/Lightweight-Segmentation)   |


### iOS:
- 从 "android_YOLOV5_NCNN\app\src\main\assets" 复制 .param 和 .bin 文件到 "iOS_YOLOv5NCNN\YOLOv5NCNN\res" 下。
- iOS如果提示 net.h 找不到的需要去ncnn官网下载或自行编译.framework替换到工程中，opencv2.framework如果有用到也需要重新下载并替换到工程。
- iOS默认使用的库不包含vulkan与bitcode。

### Android：
* 由于手机性能、图像尺寸等因素导致FPS在不同手机上相差比较大。该项目主要测试NCNN框架的使用，具体模型的转换可以去NCNN官方查看转换教程。<br/>
* 由于opencv库太大只保留 arm64-v8a/armeabi-v7a 有需要其它版本的自己去官方下载。
* ncnn暂时使用vulkan版本，在加载前需要打开加速，本项目中没有打开。如果要用ncnn版本需要修改CMakeLists.txt配置。
* AS版本不一样可能编译会有各种问题，如果编译错误无法解决、建议使用AS4.0以上版本尝试一下。

懒人本地转换(不会上传模型): [xxxx -> ncnn] https://convertmodel.com/

感谢:<br/>
- sunnyden, dog-qiuqiu, ..., nihui
- https://github.com/Tencent/ncnn

