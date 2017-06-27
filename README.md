# RippleButton
水波纹兼容
5.0以下是没有水波纹效果的

方法一：
1.style.xml中设置

  <style name="RippleButton">
    <item name="android:background"></item>
  </style>

2.在/res/drawable-v21中新建ripple.xml

  <?xml version="1.0" encoding="utf-8"?>
  <ripple xmlns:android="http://schemas.android.com/apk/res/android"
    android:color="@color/colorAccent">
    <item android:drawable="@color/colorPrimaryDark" />
  </ripple>

3.在/res/drawable中新建ripple.xml，如果不写该文件，会在5.0以下直接崩溃

  <?xml version="1.0" encoding="utf-8"?>
  <selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@color/colorPrimaryDark" android:state_pressed="false" />
    <item android:drawable="@color/colorAccent" android:state_pressed="true" />
  </selector>

4.设置Button的background为ripple.xml
	
方法二：
1.style.xml中设置

  <style name="RippleButton">
    <item name="colorControlHighlight">@color/colorAccent</item>
    <item name="colorButtonNormal">@color/colorPrimaryDark</item>
  </style>
  
上面的colorControlHighlight代表点击状态的颜色
colorButtonNormal代表正常状态的颜色
此方法可以兼容5.0以下的API

2.设置Button的Theme为RippleButton
