---
title: GUI操作系统设计
---

# GUI操作系统设计

整体的想法应该还是2D的屏幕和普通的交互方式，主要是可以提供多种选择供用户挑选，默认为最常用的那一种。

设置可以保存为各种不同的选项 一键切换。

- 文件系统（用户数据和系统数据完全隔离 app数据由app开发者管理 基本上是沙盒模式） 硬盘（分区支持良好）用户数据备份与恢复
- 屏幕显示 色彩管理
- App
    - UI 窗口、组件
    - UX 触控板键盘
- 进程
    - （进程的终止应该是瞬间的）

目标：

- 现代的个人高效率桌面GUI操作系统
- 以使用操作系统的人为主体考虑需要设计的功能
- 不考虑操作系统内核 假设内核能够提供上层应用所需的全部功能
- 不包含具体的代码逻辑实现
- 以macOS为基础 在其上提出创新设计思路
- 不太需要考虑标准的遵守 可以自己制定标准
- 可以不简单 使用起来高效就可以

立体的三维的，打开一个抽屉文件夹抽屉从屏幕伸出来。能不能模拟从文件袋中取文件的方式呢 全息显示？虚拟成像技术 是啊 做成虚拟的怎么样

三维的鼠标？？用手指或眼球指定位置？

还需要按钮吗

屏幕可以去掉了 只有键盘 键盘上部可以放VR投影仪

在键盘上写字 我可以拿着空气写吗？只要有摄像头去识别手势就可以了

---

## Hardware

RISC-V芯片 电路设计级别足够支持操作系统运行

还是在macOS平台上做个模拟吧 可以自定义标准

## 个人桌面电脑

- 不需要多用户登陆 一个电脑只有一人在使用 与手机类似
- 最少支持中文和英文
- 对命令行程序和GUI程序有良好支持

主要是UI和交互的设计

## 交互

交互：现在的话就是键盘和鼠标 之后能有更多的嘛？主要是手和手指 触控板将这一点发挥到极致

其他的比如眼睛

## 应用程序

沙盒程序，几乎所有操作都需要经过系统 应用授权的方面增多
可以生成如MIUI12的隐私报告

## 键盘

键盘以苹果官网给出的中文和英文键盘为主 去掉不需要的按键 不支持指纹解锁 不带小数字键盘

```
esc  F1 F2 F3 F4 F5 F6 F7 F8 F9 F10 F11 F12  lock
`~  1! 2@ 3# 4$ 5% 6^ 7& 8* 9( 0)  -_ =+ del
tab  Q W E R T Y U I O P  [{ ]} \|
capslock  A S D F G H J K L  ;: '"  enter
sft  Z X C V B N M  ,< .> /?  sft
fn ctrl opt cmd  space  cmd opt  left up&down right
```

字符编码不支持emoji等带图形的文字

## 快捷键

快捷键分类：

- 单一按键
- 双重按键
- 组合按键

快捷键展示：

- 存在一个系统UI展示应用以及系统的所有快捷键拦截行为

系统的各个应用应该支持快捷键

## 锁屏

支持自定义壁纸 可以选择是否和桌面壁纸相同

## 右键

右键菜单的多样化处理
macOS的菜单使用分隔符对栏目进行划分，菜单栏一般为单列。但这样导致菜单栏过长

## 聚焦搜索

可以用来快速键入符号
比如搜索「约等于」回车就可以在当前输入框的光标处输入一个约等于号

## 支持拖放

## 鼠标图标可以自行替换

## 数据安全

全盘备份