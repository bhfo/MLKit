# MLKit

[![Download](https://img.shields.io/badge/download-App-blue.svg)](https://raw.githubusercontent.com/jenly1314/MLKit/master/app/release/app-release.apk)
[![MavenCentral](https://img.shields.io/maven-central/v/com.github.jenly1314.MLKit/mlkit-common)](https://repo1.maven.org/maven2/com/github/jenly1314/MLKit)
[![JitPack](https://jitpack.io/v/jenly1314/MLKit.svg)](https://jitpack.io/#jenly1314/MLKit)
[![CircleCI](https://circleci.com/gh/jenly1314/MLKit.svg?style=svg)](https://circleci.com/gh/jenly1314/MLKit)
[![API](https://img.shields.io/badge/API-21%2B-blue.svg?style=flat)](https://android-arsenal.com/api?level=21)
[![License](https://img.shields.io/badge/license-Apche%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

[![MavenCentral](https://img.shields.io/maven-central/v/com.github.jenly1314.MLKit/mlkit-common?logo=sonatype)](https://repo1.maven.org/maven2/com/github/jenly1314/MLKit)
[![JitPack](https://img.shields.io/jitpack/v/github/jenly1314/MLKit?logo=jitpack)](https://jitpack.io/#jenly1314/MLKit)
[![CI](https://img.shields.io/github/actions/workflow/status/jenly1314/MLKit/build.yml?logo=github)](https://github.com/jenly1314/MLKit/actions/workflows/build.yml)
[![Download](https://img.shields.io/badge/download-APK-brightgreen?logo=github)](https://raw.githubusercontent.com/jenly1314/MLKit/master/app/release/app-release.apk)
[![API](https://img.shields.io/badge/API-21%2B-brightgreen?logo=android)](https://developer.android.com/guide/topics/manifest/uses-sdk-element#ApiLevels)
[![License](https://img.shields.io/github/license/jenly1314/MLKit?logo=open-source-initiative)](https://opensource.org/licenses/LICENSE-2-0)

ML Kit是一个能够将谷歌专业的机器学习知识带到应用中的极其简单易用的封装包。无论您是否有机器学习的经验，您都可以在几行代码中实现您想要的功能。甚至，您无需对神经网络或者模型优化有多深入的了解，也能完成您想要做的事情。

基于现有的API您可以很轻松的实现文字识别、条码识别、图像标签、人脸检测、对象检测等功能；另一方面，如果您是一位经验丰富的ML开发人员，ML Kit甚至提供了便利的API，可帮助您在移动应用中使用自定义的TensorFlow Lit模型。

## 效果展示

![Image](GIF.gif)

因为功能太多，所以仅录制演示了部分功能

> 你可以直接下载 [演示App](https://raw.githubusercontent.com/jenly1314/MLKit/master/app/release/app-release.apk) 体验效果

## 各Module相关说明

### [app](app)

示例App：主要用于提供MLKit各个子库的演示效果

### ~mlkit-camera-core~ 已移除（从2.0.0版本开始改用 [CameraScan](https://github.com/jenly1314/CameraScan)）

Camera：为各个子库提供相机预览分析的核心库

> 参见[CameraX](https://developer.android.google.cn/training/camerax)

### [mlkit-common](mlkit-common)

公共库：介于Camera与各个子库之间，为各个字库提供公共业务，从而简化各子库的实现

### [mlkit-barcode-scanning](mlkit-barcode-scanning)

条码扫描：通过分析图像能够识别条码的内容信息

> 参见[barcode-scanning](https://developers.google.cn/ml-kit/vision/barcode-scanning)

### [mlkit-face-detection](mlkit-face-detection)

人脸检测：通过分析图像能够检测到人脸和分析面部轮廓关键点信息

> 参见[face-detection](https://developers.google.cn/ml-kit/vision/face-detection)

人脸网格检测：通过分析图像能够检测到人脸网格信息

> 参见[face-mesh-detection](https://developers.google.cn/ml-kit/vision/face-mesh-detection)

### [mlkit-image-labeling](mlkit-image-labeling)

图像标签：通过分析图像能够标记一般对象、场所、动物种类、产品等

> 参见[image-labeling](https://developers.google.cn/ml-kit/vision/image-labeling)

### [mlkit-object-detection](mlkit-object-detection)

对象检测：通过分析图像能够检测出图像中的对象的位置信息（一张图最多可以检测五个对象）

> 参见[object-detection](https://developers.google.cn/ml-kit/vision/object-detection)

### [mlkit-pose-detection](mlkit-pose-detection)

姿势检测：通过分析图像能够检测人物摆姿势的关键点信息

> 参见[pose-detection](https://developers.google.cn/ml-kit/vision/pose-detection)

### [mlkit-pose-detection-accurate](mlkit-pose-detection-accurate)

姿势检测（精确版）：通过分析图像能够检测人物摆姿势的关键点信息（精确版的依赖库也略大一点）

> 参见[pose-detection](https://developers.google.cn/ml-kit/vision/pose-detection)

### [mlkit-segmentation-selfie](mlkit-segmentation-selfie)

自拍分割：通过分析图像能够将自拍照的人物特征进行分割

> 参见[selfie-segmentation](https://developers.google.cn/ml-kit/vision/selfie-segmentation)

### [mlkit-text-recognition](mlkit-text-recognition)

文字识别：识别图像中的文字信息

> 参见[text-recognition](https://developers.google.cn/ml-kit/vision/text-recognition/v2)

## 引入

### Gradle:

1. 在Project的 **build.gradle** 或 **setting.gradle** 中添加远程仓库

    ```gradle
    repositories {
        //...
        mavenCentral()
    }
    ```

2. 在Module的 **build.gradle** 中添加依赖项

    ```gradle

    //公共库 (*必须)
    implementation 'com.github.jenly1314.MLKit:mlkit-common:2.3.0'

    //--------------------------

    //条码识别 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-barcode-scanning:2.3.0'

    //人脸检测 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-face-detection:2.3.0'

    //人脸网格检测 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-face-mesh-detection:2.3.0'

    //图像标签 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-image-labeling:2.3.0'

    //对象检测 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-object-detection:2.3.0'

    //姿势检测 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-pose-detection:2.3.0'

    //姿势检测精确版 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-pose-detection-accurate:2.3.0'

    //自拍分割 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-segmentation-selfie:2.3.0'

    //文字识别 (可选)
    implementation 'com.github.jenly1314.MLKit:mlkit-text-recognition:2.3.0'

    ```

### 温馨提示

#### 关于MLKit版本与编译的SDK版本要求

> 使用 **v2.1.x** 以上版本时，要求 **compileSdkVersion >= 34**

> 使用 **v2.0.x** 以上版本时，要求 **compileSdkVersion >= 33**

> 如果 **compileSdkVersion < 33** 请使用 [**v1.x版本**](https://github.com/jenly1314/MLKit/tree/1.x/)

## 使用

### 版本变化说明

#### 2.x版本的变化

从 **1.x** 到 **2.x** 主要变化如下：

* 1.x版本的 **mlkit-camera-core** 核心基础库被移除了；
> 从2.0.0版本开始改为依赖[CameraScan](https://github.com/jenly1314/CameraScan)；（[CameraScan](https://github.com/jenly1314/CameraScan)是一个独立的库，单独进行维护）

* 1.x版本 **mlkit-barcode-scanning** 中的 **ViewfinderView** 被移除了；
> 从2.0.0版本开始改为依赖[ViewfinderView](https://github.com/jenly1314/ViewfinderView)；（[ViewfinderView](https://github.com/jenly1314/ViewfinderView)是一个独立的库，单独进行维护）

基于以上两点主要差异：2.x的主要使用方式和1.x基本类似，部分细节有所变更。

> 如果你是从 **1.x** 版本升级至 **2.x** 版本，那么你需要知道上面所说的差异；特别是独立出去单独维护的库，其包名都有所变化，这一点需要注意一下，大部分变动只需变更导入的包名即可完成升级。

> 如果你使用的是1.x版本的话请直接[查看v1.x分支版本](https://github.com/jenly1314/MLKit/tree/1.x/)

#### 2.x版本的使用

2.x的实现主要是以[CameraScan](https://github.com/jenly1314/CameraScan)作为基础库去实现具体的分析检测功能，所以你可以直接去看[CameraScan](https://github.com/jenly1314/CameraScan)的使用说明，只要知道了[CameraScan](https://github.com/jenly1314/CameraScan)是怎么用的，自然就会使用MLKit里面所有的子模块了。

### 各个子模块的核心类说明

下面就列一下各个子模块实现的具体功能和核心类；主要包括实现对应功能的 **Analyzer** 和便于快速实现扫描检测的 **BaseCameraScanActivity** 或 **BaseCameraScanFragment** 的子类。

| 功能        | 所属子模块                        | 对应的Analyzer实现                 | 对应的BaseCameraScanActivity子类                    |
|:----------|:---------------------------------|:------------------------------|:---------------------------------------------------|
| 条码扫描      | mlkit-barcode-scanning           | BarcodeScanningAnalyzer       | BarcodeCameraScanActivity/QRCodeCameraScanActivity |
| 人脸检测      | mlkit-face-detection             | FaceDetectionAnalyzer         | FaceCameraScanActivity                             |
| 人脸网格检测   | mlkit-face-mesh-detection        | FaceMeshDetectionAnalyzer     | FaceMeshCameraScanActivity                         |
| 图像标签      | mlkit-image-labeling             | ImageLabelingAnalyzer         | ImageCameraScanActivity                            |
| 对象检测      | mlkit-object-detection           | ObjectDetectionAnalyzer       | ObjectCameraScanActivity                           |
| 姿势检测      | mlkit-pose-detection             | PoseDetectionAnalyzer         | PoseCameraScanActivity                             |
| 姿势检测（精确版） | mlkit-pose-detection-accurate | AccuratePoseDetectionAnalyzer | AccuratePoseCameraScanActivity                     |
| 自拍分割      | mlkit-segmentation-selfie        | SegmentationAnalyzer          | SegmentationCameraScanActivity                     |
| 文字识别      | mlkit-text-recognition           | TextRecognitionAnalyzer       | TextCameraScanActivity                             |

>  **xxx** CameraScanActivity 和 **xxx** BaseCameraScanFragment 在上面只列出了一个，因为有一个 **xxx** CameraScanActivity 就有一个与之对应的 **xxx** CameraScanFragment；命名前缀一样，使用方式也基本一样。

### 条形码检测分析示例（**mlkit-barcode-scanning**）

#### 支持检测识别的条形码格式主要有：
  * 线性格式：Codabar, Code 39, Code 93, Code 128, EAN-8, EAN-13, ITF, UPC-A, UPC-E
  * 2D格式：Aztec, Data Matrix, PDF417, QR Code

```kotlin
BarcodeDecoder.process(bitmap).addOnSuccessListener(this) {
   if (it.isNotEmpty()) {
      // TODO 成功；此处可获取识别的结果
   } else {
      // TODO 没有结果
   }
}.addOnFailureListener(this) {
   // TODO 失败；出现异常
}
```

### 各个module的使用示例

#### mlkit-common （1.3.0新增）

公共库：介于Camera与各个子库之间，为各个字库提供公共业务，从而简化各子库的实现。

#### mlkit-barcode-scanning

扫条形码/二维码实现示例：通过直接继承 **BarcodeCameraScanActivity** 实现的示例
[BarcodeScanningActivity](app/src/main/java/com/king/mlkit/vision/app/barcode/BarcodeScanningActivity.kt)

扫二维码实现示例：通过间接继承 **BarcodeCameraScanActivity** 实现的示例
[QRCodeScanningActivity](app/src/main/java/com/king/mlkit/vision/app/barcode/QRCodeScanningActivity.kt)

扫二维码（多个结果）实现示例：通过间接继承 **BarcodeCameraScanActivity** 实现的示例
[MultipleQRCodeScanningActivity](app/src/main/java/com/king/mlkit/vision/app/barcode/MultipleQRCodeScanningActivity.kt)

#### mlkit-face-detection

人脸检测实现示例：通过直接继承 **FaceCameraScanActivity** 实现的示例
[FaceDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/face/FaceDetectionActivity.kt)

多人脸检测实现示例：通过间接继承 **FaceCameraScanActivity** 实现的示例
[MultipleFaceDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/face/MultipleFaceDetectionActivity.kt)

#### mlkit-face-mesh-detection （1.2.0新增）

人脸网格检测实现示例：通过直接继承 **FaceMeshCameraScanActivity** 实现的示例
[FaceMeshDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/face/FaceMeshDetectionActivity.kt)

#### mlkit-image-labeling

图像标签实现示例：通过直接继承 **ImageCameraScanActivity** 实现的示例
[ImageLabelingActivity](app/src/main/java/com/king/mlkit/vision/app/image/ImageLabelingActivity.kt)

#### mlkit-object-detection

对象检测实现示例：通过直接继承 **ObjectCameraScanActivity** 实现的示例
[ObjectDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/object/ObjectDetectionActivity.kt)

多对象检测实现示例：通过间接继承 **ObjectCameraScanActivity** 实现的示例
[MultipleObjectDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/object/MultipleObjectDetectionActivity.kt)

#### mlkit-pose-detection

姿势检测实现示例：通过直接继承 **PoseCameraScanActivity** 实现的示例
[PoseDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/pose/PoseDetectionActivity.kt)

#### mlkit-pose-detection-accurate

姿势检测（精确版）实现示例：通过间接继承 **AccuratePoseCameraScanActivity** 实现的示例
[AccuratePoseDetectionActivity](app/src/main/java/com/king/mlkit/vision/app/pose/AccuratePoseDetectionActivity.kt)

#### mlkit-segmentation-selfie

自拍分割实现示例：通过直接继承 **SegmentationCameraScanActivity** 实现的示例
[SelfieSegmentationActivity](app/src/main/java/com/king/mlkit/vision/app/segmentation/SelfieSegmentationActivity.kt)

#### mlkit-text-recognition

文字识别实现示例：通过直接继承 **TextCameraScanActivity** 实现的示例
[TextRecognitionActivity](app/src/main/java/com/king/mlkit/vision/app/text/TextRecognitionActivity.kt)

### 模型配置（可选）

关于依赖项下载模型（如果选择使用 Google Play Services 中的模型）则可以通过在AndroidManifest中申明配置

```xml

<meta-data android:name="com.google.firebase.ml.vision.DEPENDENCIES"
    android:value="ocr" /><!-- To use multiple models: android:value="ocr,model2,model3" -->
```

如：配置Barcode模型、Face模型、OCR模型等等~

```xml

<meta-data android:name="com.google.firebase.ml.vision.DEPENDENCIES"
    android:value="barcode,face,ocr" />
```

更多使用详情，请查看[app](app)中的源码使用示例或直接查看 [API帮助文档](https://jenly1314.github.io/MLKit/api/)

### 其他

#### ABI过滤

在Module的 **build.gradle** 里面的 android{} 中设置支持的 SO 库架构（可选，支持多个平台的 so，支持的平台越多，APK体积越大）

```gradle
    defaultConfig {

        //...

        ndk {
            //设置支持的 SO 库架构（开发者可以根据需要，选择一个或多个平台的 so）
            abiFilters 'armeabi-v7a' // , 'arm64-v8a', 'x86', 'x86_64'
        }
    }
```

#### JDK版本

需使用JDK8+编译，在你项目中的build.gradle的android{}中添加配置：

```gradle
compileOptions {
    sourceCompatibility JavaVersion.VERSION_1_8
    targetCompatibility JavaVersion.VERSION_1_8
}
```

## 相关推荐

- [ZXingLite](https://github.com/jenly1314/ZXingLite) 基于zxing实现的扫码库，优化扫码和生成二维码/条形码功能。
- [WeChatQRCode](https://github.com/jenly1314/WeChatQRCode) 基于OpenCV开源的微信二维码引擎移植的扫码识别库。
- [CameraScan](https://github.com/jenly1314/CameraScan) 一个简化扫描识别流程的通用基础库。
- [ViewfinderView](https://github.com/jenly1314/ViewfinderView) ViewfinderView一个取景视图：主要用于渲染扫描相关的动画效果。
- [LibYuv](https://github.com/jenly1314/libyuv) 基于Google的libyuv编译封装的YUV转换工具库，主要用途是在各种YUV与RGB之间进行相互转换、裁减、旋转、缩放、镜像等。
- [LogX](https://github.com/jenly1314/LogX) 一个小而美的日志记录框架；好用不解释。

<!-- end -->

## 版本日志

#### v2.3.0：2025-1-15
* 更新CameraScan至v1.3.0
* 更新MLKit相关依赖库版本

#### [查看更多版本日志](CHANGELOG.md)

---

![footer](https://jenly1314.github.io/page/footer.svg)
