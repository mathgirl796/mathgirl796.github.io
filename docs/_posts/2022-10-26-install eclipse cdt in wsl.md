更新你的显卡驱动（随便更一下就行，只是怕他版本太老了）

进入cmd，执行

```shell
wsl --update
wsl --shutdown
```

然后下载并解压eclipse cdt

```shell
cd ~
mkdir softwares
cd softwares
wget https://mirrors.neusoft.edu.cn/eclipse/technology/epp/downloads/release/2022-09/R/eclipse-cpp-2022-09-R-linux-gtk-x86_64.tar.gz
tar zxvf eclipse-cpp-2022-09-R-linux-gtk-x86_64.tar.gz
./eclipse/eclipse
```

这时你会发现打开失败，这是因为相关图形化库没有安装。其实，查看微软关于wsl界面程序的官方教程可知，官方仅支持该教程中列举的几款软件。但是安装这些软件，就会同时给你安装上图形界面的运行库（仅测试了gedit和nautilus）。教程网址如下：

```
https://learn.microsoft.com/zh-cn/windows/wsl/tutorials/gui-apps
```

这里推荐gedit。gedit类似于记事本，可以解决不会用vim的问题

nautilus是一个linux文件管理器，但是它不能连接windows的文件系统，也不能在windows的文件管理器和它之间互相拖文件。它的作用大概就是在里面找到你想要去的linux上的某个文件夹，然后Ctrl+L、Ctrl+C，复制路径，然后回到wsl里cd这个路径，这样会方便一点。nautilus甚至不能新建文件，只能新建文件夹，查看隐藏文件的开关也点不了（也许进一步配置一下就可以了）。总之不推荐nautilus。

以上所说的浏览文件的功能其实很好实现，直接在wsl中执行以下命令即可，没必要安装nautilus。虽然在linux上执行xxx.exe显得很诡异。

```shell
explorer.exe 你要打开的路径
```

然后再执行你的~/softwares/eclipse/eclipse就行了

