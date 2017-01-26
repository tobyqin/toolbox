# 我的工具箱
## 前言

此仓库收集了一些我觉得还不错的小工具，收集的标准如下：

1. 用起来比较顺手，能快速解决某种问题
2. 如果需要上传，大小不超过 5 MB
3. 无流氓，后门行为的

[TOC]

## 效率篇

### 1. MouseInc

[MouseInc](http://www.shuax.com) 是一款鼠标增强软件。

**增强功能**

- 鼠标手势：按住右键滑动即可，可以显示鼠标轨迹和动作。
- 滚轮穿透：可以直接滚动悬停下方的非激活窗口。不兼容UWP程序，会导致无法滚动。
- 自然滚动：使得原来的随滚动条移动改变为随内容移动。（滚轮反向）
- 突破边界：让鼠标突破屏幕边界，在屏幕边缘时跳到另一边。
- 音量控制：按住自定义的超级键时，滚轮上下滚动，调节音量大小；按下滚轮，切换禁音状态。
- 移动窗口：按住自定义的超级键时，可使用拖拽方式移动当前窗口。

所有配置保存在MouseInc.ini文件中，注释应该能帮助你。
推荐使用具有高亮功能的编辑器修改，例如notepad2。

**收集理由：**

很早以前我就已经开始使用鼠标手势，不过仅限于浏览器范围。最初是Opera浏览器的粉丝，默认集成了鼠标手势，到后来的Firefox，Chrome浏览器，我都优先安装了鼠标手势的插件。不得不承认，当你在浏览屏幕上的信息时，大部分时候鼠标的效率操作效率会比键盘高，毫不夸张地说，鼠标手势可以让你的鼠标操作提高不止一个等级。

MouseInc可以让你在任何程序使用鼠标手势，而不仅限于浏览器内。如果你用了MouseInc，那么浏览器中的鼠标手势插件就可以退休了，有了MouseInc你就可以在Firefox，Chrome，IE这些浏览器使用相同的鼠标手势。

但是，我选择它的原因其实并不是因为它真的很好，而是因为自从换了Macbook后，所有的浏览器鼠标手势插件都和触摸板Touchpad的手势冲突，导致右键失灵。所以不得已我忍痛禁用了Firefox上的FireGuestures，Chrome里的crxMouse，无奈我在Windows还是不习惯没有鼠标手势的日子。

当我招到MouseInc有种泪流满面的感觉，我又可以愉快地用鼠标手势了，而且不仅仅在浏览器中。

MouseInc的配置：

默认的MouseInc手势配置和我们常见的手势并不一样，所以你可以和我一样，需要进行一些修改。

```
[SuperKey]
;超级键功能，具体的按键在上面设置

;按住SuperKey时，可使用拖拽方式移动当前窗口
SuperDrag=0
```

关闭超级拖拽，因为按住alt键加鼠标左键在很多IDE中是选择纵向选择的作用

```
[SuperKey]
;如果当前程序在列表中，则鼠标手势不生效
[MouseGestureExclude]
explorer.exe
```

在文件管理器中关闭鼠标手势，因为我需要默认的右键选择拖动。

```
[GlobalGesture]
;全局鼠标手势设置，支持的手势方向：↑↓←→↗↘↙↖
;格式为：方向=动作，动作在 Script\Gesture.lua 中定义
;→←=Calc
;↑=TopWindow
;↓=NoTopWindow
;→↓=MinimizeWindow
;→↑=MaximizeWindow
;←→=RestoreWindow
;→=CloseWindow
;←=CloseSimilarWindow
;↑↓=CenterWindow
;→↓←=Exit
↓=MinimizeWindow
↑=MaximizeWindow
↓→=CloseTab
→←→=CloseWindow
↑↓=RestoreWindow

[GestureChrome]
;自定义程序的鼠标手势操作，本项会在操作Chrome.exe时生效
;在这里定义的命令会优先于全局手势中的设置
↑→=RightTab
↑←=LeftTab
→=Forward
←=Backward
↓→=CloseTab
↓←=ReopenTab
↓↑=Refresh
```
修改为常见和我觉得顺手的鼠标手势。