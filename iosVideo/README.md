## 1、接受一个历史遗留问题
本地安全帽的音频和视频在android可以使用，在ios下不可使用的问题
解决思路： 1、调试，打印相关信息， 2、 由于视频流和mp4很接近， 使用一个mp4文件，定位是视频本身就播放不出来还是其他的问题 
          3、通过第二步，判断mp4视频可以存在，但是样式存在问题，视频本身比较小并且默认是底色是白色。 通过修改样式，使视频内容更加明显展示。
          4、 通过调试，判断帽子视频已经加载成功。 但是并没有播放。
          5、通过查找资料确定ios下限制了自动播放功能。
          6，添加代码手动播放帽子视频，视频可以播放成功。解决问题。
          7、调整样式和语音的功能，是功能兼容性更强，功能更完善。



## 2、 遇到的问题以及解决办法

>   本地调试比较困难，项目是使用uni-app开发的，但是视频的功能是一个H5页面，在H5页面console无法打印出来
    解决： H5和app有一个message的方法，在H5主动发出一个事件，app可以接受。 所以在H5写一个方法，接受一个字符串，然后向上暴露给app,由app来打印出来。

>   播放视频代码
    解决：this.instance.play()

## 2、 拓展
目前是视频建立成功之后，添加setTimeout三秒之后进行播放视频。 但是授权是有一个弹框，如果授权不够及时，超出3s,是否会引发无法播放问题，需要退出重进的才行。目前只在一处添加了自动播放，并未对其他地方做处理。所以正常的是可以使用。