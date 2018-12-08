# NiceImageView

### 效果预览

|![](images/r1.PNG)|![](images/r2.PNG)|![](images/r3.PNG)|
|---|---|---|
|![](images/c1.PNG)|![](images/c2.PNG)|![](images/c3.PNG)|
### 特点
* 基于AppCompatImageView扩展
* 支持圆角、圆形显示
* 可绘制边框，圆形时可绘制内外两层边框
* 支持边框不覆盖图片
* 可绘制遮罩
* ......
### 基本用法
**Step 1. 添加JitPack仓库**
在项目根目录下的 `build.gradle` 中添加仓库:
``` gradle
allprojects {
    repositories {
        ...
        maven { url "https://jitpack.io" }
    }
}
```
**Step 2. 添加项目依赖**
``` gradle
dependencies {
    implementation 'com.github.SheHuan:NiceImageView:1.0.5'
}
```
**Step 3. 在布局文件中添加CornerLabelView**
```
<com.shehuan.niv.NiceImageView
    android:layout_width="200dp"
    android:layout_height="200dp"
    android:layout_marginTop="10dp"
    android:src="@drawable/cat"
    app:border_color="#FF7F24"
    app:border_width="4dp"
    app:is_circle="true" />
```
### 支持的属性、方法
|属性名|含义|默认值|对应方法
|---|---|---|---|
|is_circle|是否显示为圆形（默认为矩形）|false|isCircle()
|corner_top_left_radius|左上角圆角半径|0dp|setCornerTopLeftRadius()
|corner_top_right_radius|右上角圆角半径|0dp|setCornerTopRightRadius()
|corner_bottom_left_radius|左下角圆角半径|0dp|setCornerBottomLeftRadius()
|corner_bottom_right_radius|右下角圆角半径|0dp|setCornerBottomRightRadius()
|corner_radius|统一设置四个角的圆角半径|0dp|setCornerRadius()
|border_width|边框宽度|0dp|setBorderWidth()
|border_color|边框颜色|#ffffff|setBorderColor()
|inner_border_width|相当于内层边框（is_circle为true时支持）|0dp|setInnerBorderWidth()
|inner_border_color|内边框颜色|#ffffff|setInnerBorderColor()
|is_cover_src|border、inner_border是否覆盖图片内容|false|isCoverSrc()
|mask_color|图片上绘制的遮罩颜色|不设置颜色则不绘制|setMaskColor()

### 其它
如果你需要实现类似钉钉的圆形组合头像，例如：

![](images/d3.PNG)

可以先生成对应的Bitmap，并用圆形的 NiceImageView 显示即可。如何生成组合Bitmap可以参考这里：[CombineBitmap](https://github.com/Othershe/CombineBitmap)