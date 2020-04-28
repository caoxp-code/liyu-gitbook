# 统一样式大小设置

## 为什么需要统一设置

由于我拿到的设计稿一般为750*1334px的资源，为了在不同的分辨率手机中，实现效果一致，需要将设计稿中的尺寸换算成不同手机上的尺寸，这样不会出现由于手机变大，而展示的组件偏小的问题。

## 怎么实现

由于手机密度比的问题，我们需要将设计稿中的px换算成dp。比如我的设计稿是740*1334px。

通过MediaQuery.of(context)获取到当前屏幕信息。

计算宽度缩放比

```
MediaQueryData _mediaQueryData = MediaQuery.of(context);
double get scaleWidth => _mediaQueryData.size.width / 750;
// 此处返回的width即为当前手机上的宽度
double setWidth(double width) => width * scaleWidth; 
```
