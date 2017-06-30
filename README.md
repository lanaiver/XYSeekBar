# XYSeekBar
这是一个自定义的双向滑动条，通过onDraw()画出布局onTouchEvent()监听滑动实时更新布局
布局主要包括 2个圆形滑动块、 2条不同背景颜色条、 2个Paint显示当前滑动百分比

使用步骤跟自定义view一样
把app项目中的SeekBarPressure类拷贝到项目中，
xml中添加自定义布局，有需要把图片和背景条下载下，
当然也可以通过shape自己画

经常有人问：
比如希望刻度从0-200
比如希望刻度从18-55

其实主要控制刻度的就下面几句代码

    mOffsetLow = formatInt(defaultScreenLow / 100 * (mDistance)) + mThumbWidth / 2;
    mOffsetHigh = formatInt(defaultScreenHigh / 100 * (mDistance)) + mThumbWidth / 2;
    //当前滑块刻度
    double progressLow = formatInt((mOffsetLow - mThumbWidth / 2) * 100 / mDistance);
    double progressHigh = formatInt((mOffsetHigh - mThumbWidth / 2) * 100 / mDistance);
    //如果希望刻度从0-200，把上面的100改成200就行 
 
     //如果希望刻度从18-55，
     mOffsetLow = formatInt(defaultScreenLow / 100 * (mDistance)) + mThumbWidth / 2;
     mOffsetHigh = formatInt(defaultScreenHigh / 100 * (mDistance)) + mThumbWidth / 2;
     //当前滑块刻度
     double progressLow = formatInt((mOffsetLow - mThumbWidth / 2) * 100 / mDistance);
     double progressHigh = formatInt((mOffsetHigh - mThumbWidth / 2) * 100 / mDistance);


最后注意一下：在xml中SeekbarPressure的父布局必须是LinearLayout
请设置SeekbarPressure的宽为match_parent。宽高用父容器来限制。

如果其他问题可QQ 332256483 滑动条
http://www.iyuyao.top/index.php/post/34.html
