### IDEA系列开启全局菜单

我发查询日志文件的时候发现了

日志文件可以从 `Help -> Show Log In Dolphin` 直接查看

```
2020-10-24 10:09:36,692 [ 10789] INFO - penapi.wm.impl.GlobalMenuLinux - can't start main loop via JavaFX (will run it manually): com.sun.javafx.application.PlatformImpl
```

这里不太对啊，人家是缺少库，我这怎么成了无法通过JavaFX启动主循环

我就猜测应该是IDEA找不到JavaFX，然后无法调用JavaFX的API



这里我就想到了几种可能可以解决的办法

- 一个，去JavaFX的官网查询一下
- 二个，去看看IDEA里有没有JavaFX的插件
- ...

近水楼台先得月，我IDEA都打开了，就打开插件市场搜一下呗

果然让我找到了一个很像的东西：

![img](https://i.loli.net/2020/10/24/UhLnz12qluwZMEg.png)

这个插件可以让IDEA的其他插件可以调用JavaFX的API

安装之后重启可以看到

![img](https://i.loli.net/2020/10/24/C5vVK3rUZXJapd9.png)

全局菜单已经能够工作。