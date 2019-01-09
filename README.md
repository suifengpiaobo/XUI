<p align="center">
  <img src="https://github.com/xuexiangjys/XUI/blob/master/art/app_logo_xui.png" width="388" height="321" alt="Banner" />
</p>

# XUI
[![xui][xuisvg]][xui]  [![api][apisvg]][api]

一个简洁而又优雅的Android原生UI框架，解放你的双手！

> 涵盖绝大部分的UI组件：TextView、Button、EditText、ImageView、Spinner、Picker、Dialog、PopupWindow、MarqueeView、ProgressBar、LoadingView、StateLayout、FlowLayout、SearchView、Switch、Actionbar、TabBar、Banner、GuideView、BadgeView、WebView等一系列的组件和丰富多彩的样式主题。

## 关于我

[![github](https://img.shields.io/badge/GitHub-xuexiangjys-blue.svg)](https://github.com/xuexiangjys)   [![csdn](https://img.shields.io/badge/CSDN-xuexiangjys-green.svg)](http://blog.csdn.net/xuexiangjys)

----

## 特征

* 简洁优雅，尽可能少得引用资源文件的数量，项目库整体大小不足1M(打包后大约644k）
* 组件丰富，提供了绝大多数我们在开发者常用的功能组件。
* 使用简单，为方便快速开发，提高开发效率，对api进行了优化，提供一键式接入。
* 样式统一，框架提供了一系列统一的样式，使UI整体看上去美观和谐。
* 兼容性高，框架还提供了3种不同尺寸设备的样式（4.5英寸、7英寸和10英寸），让UI兼容性更强。
* 扩展性强，各组件提供了丰富的属性和样式API，可以通过设置不同的样式属性，构建不同风格的UI。

----

## 如何使用

### 添加Gradle依赖

1.先在项目根目录的 build.gradle 的 repositories 添加:
```
allprojects {
     repositories {
        ...
        maven { url "https://jitpack.io" }
    }
}
```

2.然后在dependencies添加:

```
dependencies {
  ...
  implementation 'com.github.xuexiangjys:XUI:1.0.0'
}
```

### 初始化XUI设置

1.在Application最顶部初始化设置

```
XUI.init(this); //初始化UI框架
XUI.debug(true);  //开启UI框架调试日志

```

2.调整字体库（对字体无要求的可省略）

（1）设置你需要修改的字体库路径（assets下）
```
XUI.getInstance().initFontStyle("...");
```

（2）在项目的基础Activity中加入如下代码注入字体.

```
@Override
protected void attachBaseContext(Context newBase) {
    //注入字体
    super.attachBaseContext(CalligraphyContextWrapper.wrap(newBase));
}
```

### 调整应用的基础主题

基础主题类型：

* 大平板(10英寸, 240dpi, 1920*1200）：XUITheme.Tablet.Big

* 小平板(7英寸, 320dpi, 1920*1200）：XUITheme.Tablet.Small

* 手机（4.5英寸, 320dpi, 720*1280）：XUITheme.Phone

```
<style name="AppTheme" parent="XUITheme.Phone">
     <!-- 自定义自己的主题样式 --> 
    <item name="colorPrimary">@color/colorPrimary</item>
    <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
    <item name="colorAccent">@color/colorAccent</item>
 </style>

```
当然也可以在Activity刚开始时调用如下代码动态设置主题

```
@Override
protected void onCreate(Bundle savedInstanceState) {
    XUI.initTheme(this);
    super.onCreate(savedInstanceState);
    ...
}
```
----

## 演示

### 演示程序截图

![](./art/1_splash.png) &emsp; ![](./art/2_main.png) &emsp; ![](./art/3_about.png) &emsp; ![](./art/4_menu.png)

![](./art/5_dialog.png) &emsp; ![](./art/6_bottom_dialog.png) &emsp; ![](./art/7_picker.png) &emsp; ![](./art/8_webview.png)

![](./art/9_flowlayout.png) &emsp; ![](./art/10_ninegrid.png) &emsp; ![](./art/11_radius_imageview.png) &emsp; ![](./art/12_badge_view.png)

![](./art/13_tabview.png) &emsp;

### Demo下载

> 演示程序大概18M（主要是demo中集成了一个小视频拍摄的库比较大，大约13M左右，而XUI库目前只有644k大小），项目比较大，推荐使用蒲公英下载。

#### 蒲公英下载

[![蒲公英](https://img.shields.io/badge/downloads-蒲公英-blue.svg)](https://www.pgyer.com/XUIDemo)

![](./art/download_pugongying.png)

#### Github下载

[![Github](https://img.shields.io/badge/downloads-Github-blue.svg)](https://github.com/xuexiangjys/XUI/blob/master/apk/xuidemo.apk?raw=true)

![](./art/download_github.png)






































[xuisvg]: https://img.shields.io/badge/XUI-v1.0.0-brightgreen.svg
[xui]: https://github.com/xuexiangjys/XUI
[apisvg]: https://img.shields.io/badge/API-17+-brightgreen.svg
[api]: https://android-arsenal.com/api?level=17