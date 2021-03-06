---
title: 解决Ubuntu鼠标一直处于拖拽状态的Bug.
teaser: 鼠标一直处于拖拽状态,无法进行操作.
category: 环境Bug.
tags: [ubuntu, Bug, 鼠标]
---

# 解决Ubuntu鼠标一直处于拖拽状态, 无法操作的Bug

**环境**: **VMware@Workstation 14 PRO** & **Ubuntu 17.10**

**情况描述**: 在桌面拖拽移动文件的时候出现Bug, 文件没有拖拽成功, 有如下症状

* 结果发现鼠标指针成了一个握紧的手型, 并且一直无法取消
* 只要在桌面上就无法执行点击, 右键灯操作 一直处于拖拽状态
* 但是对于其他程序窗口可以进行关闭, 最大化, 最小化操作, 而且能够打开文件夹

	步估计可能是文件管理器之类的进程出现的问题	

**解决方法**: Google发现是nautilus的问题. 要是还能运行terminal的话,    `Ctrl + T ` 运行以下命令

```
  kill `pgrep nautilus`
```

强行终止这个进程后, 就会发现鼠标指针恢复正常, 不过**会导致一个问题**, 暂时没有解决

* 虽然鼠标指针问题得到了解决, 但是桌面文件都会消失
* 文件和图标等只是不被显示, 经过验证, 文件仍然存在于home/Desktop目录下, 并没有删除, 只是没有显示
* 状态栏和Dock栏都是可以正常操作的

---
* [ ] 尝试过重新启动`nautilus` 进程, 无效, 问题暂时搁置