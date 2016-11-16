#Xcode: Cocoa应用更换MainMenu.xib好麻烦

环境Xcode 6.1。Cocoa应用，出于默认的MainMenu.xib出了一些问题，需要重写下，于是删掉再新建一个，本以为能直接用，没想到差点累出翔。自己创建的xib费了半天劲才可以在AppDelegate里拖放创建Outlet。

是这样的，Xcode默认创建的MainMenu.xib在Interface Builder中的Objects一栏中是有App Delegate这一项的，如下图：

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-21-at-11.59.21-PM_thumb.png)

同时AppDelegate中也已经默认连接好了MainMenu.xib中的NSWindow：

``` objectivec
  
  @interface AppDelegate ()

  @property (weak) IBOutlet NSWindow *window;

  @end
  
``` 

可是如果自己创建MainMenu.xib的话，这些都是没有的。在Interface Builder中的Objects一栏是这样：

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-22-at-12.00.56-AM_thumb.png)

必须在右下的Objects Library中找到一个叫Object的项目：

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-22-at-12.01.47-AM_thumb.png)

然后，把他手动拖到Interface Builder左侧的Objects一栏内，接着多了一个Object项目：

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-22-at-12.02.09-AM_thumb.png)

然后在右上的Identity Inspector中设置Class为AppDelegate：

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-22-at-12.02.30-AM_thumb.png)

这样，Objects一栏内终于有了熟悉的AppDelegate这一项：

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-22-at-12.03.01-AM_thumb.png)

接下来，把AppDelegate设置成File’s Owner，具体步骤：按住Control，然后把Placeholders中的File’s Owner拖放到下面Objects里的App Delegate，选择delegate就OK了。

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/image_thumb11.png)

终于把新建的MainMenu.xib搞成和Xcode默认创建的一样了，一切成功后，就可以继续在Interface Builder中拖放Outlet到AppDelegate中了。

如果MainMenu.xib名字变了的话，最后别忘了在工程属性中Deployment Info把MainMenu的名字改回来，或者也可以设置Info.plist中的Main nib file base name属性。

![wireless](https://www.mgenware.com/blog/wp-content/uploads/2014/12/Screen-Shot-2014-12-22-at-12.06.10-AM_thumb.png)
