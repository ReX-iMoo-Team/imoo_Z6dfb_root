# imoo_Z6dfb_root
## 该仓库用与讲述如何root小天才z6dfb及以上版本。

- **⚠仅适用于部分有一定基础的人，不建议0基础者使用**

1. 使用[iMoo Toolkit](https://github.com/ReX-iMoo-Team/iMoo-Toolkit)安装[magisk](https://github.com/topjohnwu/Magisk/releases/tag/v23.0)到手表上。
   - **把充电特效改成流光**
   - 命令行输入: 
       ```sh
       adb shell am density 200
       ```
2. 在**QFIl**把**Boot**提取出来把文件导到手表的内部存储根目录`/sdcard/`。
   - 1.启动**QIFL**工具，确保手表进入9008模式后，选择`flat build`；
   - 2.点击`Select Programmer`选项，选择对应的文件。注意，此时的**programmer path**的版本应该和手表中的版本一致；
   - 3.点击菜单中的`tool`，选择`Partition Manager`选项；
   - 4.按照提示，点击**OK**；
   - 5.弹出窗口`Parttition Manager`，这里可以看到每个分区的起始位置，从而对分区进行管理；
   - 6.选择需要的镜像的分区[boot]，点击右键，选择Manager Partition Data；
   - 7.弹出`Raw Date Manager`窗口，选择**Read Data**；
   - 8.软件开始读取`userdata`分区；
   - 9.读取分区完成，在对应的路径即可找到导出的`boot.bin`文件，具体导出路径见`status`下输出的文件路径。
3. 打开**magisk**点击安装，选择直接选择并修补刚才传入的boot.bin文件。
   - **不要选择保留avb。**
4. 打开找到刚刚导入的`boot.bin`，**magisk**会开始修补**Boot**文件。
   - 显示**All done**就是成功。
5. 接下来到手表下载目录`/sdcard/Download/`，将`boot.img`上传到电脑上。
6. 使用**QFIl**进入**9008**，将`boot.img`刷进**recovery**里面，`misc.bin`([下载](https://github.com/ReX-iMoo-Team/imoo_Z6dfb_root/blob/main/misc/misc.bin))刷进**misc**里，确定刷完依次退出刷完之后就**root**成功了。

- **发现者:[早茶光不是找茬光](https://space.bilibili.com/1268760897)**
