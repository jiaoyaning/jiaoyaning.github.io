---
title: Android开发 ScrollView默认位置不是最顶部解决方案
date: 2017-01-22 12:49:59
tags: Android
---

## 描述：
Scrollview里面嵌套了一个listview ，这是开发中最寻常的一种布局，遇到的问题是：在这个Scrollview页面默认的起始位置不是最顶部，而是listview的底部。

------
## 原因：
1. 在Activity计算窗口的高度时，是在listview没有填充数据时候就完成的，由于ScrollView嵌套listview时没有指定高度，所以ScrollView就会按照layout中定义的默认高度计算。

2. 因为listview获取了焦点。

----
## 解决：
1. myScrollView.smoothScrollTo(0,20);
 >需在listview数据加载完成后调用

2. 在代码里去掉listview的焦点
>lv.setFocusable(false);

3. Listview外套一层LinearLayout

4. 跟EditText一样，在父元素的属性下面下下面这两行即可
>android:focusableInTouchMode="true"
android:focusable="true"

5. 最开始的时候让最上面其中一个控件获得焦点，滚动条自然就到顶部去了，如下：
>txtBaseMsg.setFocusable(true);
txtBaseMsg.setFocusableInTouchMode(true);
txtBaseMsg.requestFocus();