
# wechat_jump_ai_kotlin
---

微信小游戏 跳一跳 kotlin AI 自动寻找开始跳的坐标，目标坐标.

# 成果
---

![](https://raw.githubusercontent.com/uglyer/wechat_jump_ai_kotlin/master/pic/show.jpg?)


# 跳一跳
---

微信小程序可以玩游戏了，我们来破解一下《跳一跳》这个官方出品的小游戏吧。



# 思路
---

用usb调试安卓手机，用adb截图并用鼠标测量距离，然后计算按压时间后模拟按压。

```bash
$ adb shell input swipe <x1> <y1> <x2> <y2> [duration(ms)] (Default: touchscreen) # 模拟长按
$ adb shell screencap <filename> # 保存截屏到手机
$ adb pull /sdcard/screen.png # 下载截屏文件到本地
```

1. 得到手指按的时间 t
1. 时间 = 距离 / 速度(常量) t = L / k
1. L = p2 - p1
1. 获取到起始点和结束点的坐标

# 源码
---

开发环境： Kotlin, IetelliJ IDEA

<https://github.com/uglyer/wechat_jump_ai_kotlin>


# 使用方法
---

1. 在电脑上下载好adb
1. 打开安卓手机的usb调试模式并授权连接的电脑
1. 打开微信跳一跳，并点击开始
1. 在`Constans.kt`中配置好adb路径与截图路径，运行
1. 会自动识别完成跳跃

# 参考
---

<https://github.com/easyworld/PlayJumpJumpWithMouse>
<https://github.com/iOSDevLog/JumpJump>

# License
---

wechat_jump_ai_kotlin is released under the GPL V3 license. See LICENSE for details.