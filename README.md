感谢xda-developer知名开发者开发的AROMA-Filemanager，相信很多开发者都有使用过，它是一个recovery模式下的文件管理器，方便救砖，删除，编辑system/data/sdcard分区的文件等功能。
下面介绍下具体编译过程：

需要在cyanogenmod源码下进行编译，以cm-10.1为例

1、下载AROMA-Filemanager源码：

英文版：https://github.com/amarullz/AROMA-Filemanager

中文版：https://github.com/ruling/aromafm

2、将下载的AROMA-Filemanager源码解压并命名为aromafm，将aromafm目录复制到cm-10.1/bootable/recovery/目录下

3、修改cm-10.1/bootable/recovery/根目录下的Android.mk，在最后一句添加

include $(commands_recovery_local_path)/aromafm/Android.mk

4、然后和编译recovery.img步骤一样，编译recovery命令在终端输入以下命令：

. build/envsetup.sh

make -j16 otatools

gedit ~/.bashrc

export PATH=$PATH:~/cm10.1/out/host/linux-x86/bin

source ~/.bashrc

lunch

然后会出现设备的编号，输入编号后按回车键

make -j16 recoveryimage

5、编译完成后会在recovery输出目录产生aromafm_out目录，即是编译出来的AROMA-文件管理器。
