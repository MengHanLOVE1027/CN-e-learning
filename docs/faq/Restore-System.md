---
tags:
    - 高级
---

# 重装/还原 Windows系统/原厂镜像
> [!CAUTION]
> ⚠注意： **建议专业人员操作，除非你知道你在干什么；重装系统会将系统盘C盘和桌面文件被清空，如有重要数据，请您提前做好备份！！**重装过程大概30分钟左右，过程中**请不要断电等**。

> 以下内容图片部分来自于网络

- 一些情况下，我们可能需要对一体机进行 系统重装，以解决问题或提升系统流畅度及稳定性等，我们可以通过下面几个方法以 重新安装 Windows 系统

## 通过一体机自带的恢复程序以恢复系统

> [!WARNING]
> ⚠注意：**需要确保恢复分区完好无损且镜像文件没有被损坏等**，如果**分区不存在，镜像文件损坏等原因将无法通过此方法恢复原厂系统镜像！！！**
> 如果你不想使用原厂系统镜像，请跳转到 #使用PE进行操作

- 大部分一体机厂商都会在硬盘中划分25-30GB左右的分区空间存放原厂系统镜像，且分区被隐藏
![图片](/images/Restore-System/CloneZilla.jpg)<br>
(鸿合新款设备，使用了 再生龙 CloneZilla 方案，图片中使用的工具为DiskGenius)

>（除希沃以外（希沃的恢复分区通常是E盘且名称为 BACKUP_OS），部分厂商可能会把GHO镜像文件存放到D盘隐藏文件夹目录下，具体可以使用 DiskGenius 查看）
> 
>


- 通常这些镜像文件较大，且预装了驱动和相关资源软件等，所以恢复也需要一定的时间，好处是恢复完成后可以直接使用，无需进行其他繁琐操作如安装驱动等
### 通用（适用于大部分常见的设备）
#### 恢复按钮 / 选项
- 大部分常见的一体机设备会有一个恢复小孔按钮，部分需要使用牙签等较细的物品来操作，一部分恢复按钮在OPS主机上（如图所示）
- 在恢复之前，请确保C盘下没有重要资料文件

- 操作方法：**先将设备关机**，在关机状态下，按住恢复按钮不放，然后将设备开机，等待出现到相关恢复界面时即可放开
- 下图为部分教学一体机的恢复按钮外观位置：
> 安道Amdox
> ![Amdox](/images/Restore-System/Amdox.jpg)
> OPS上的恢复按钮
> ![Amdox_OPS](/images/Restore-System/OPS_2.jpg)
> 鸿合HiteVision
>![HiteVision](/images/Restore-System/HiteVision.jpg)
> OPS上的恢复按钮
>![HiteVision_OPS](/images/Restore-System/OPS_1.jpg)

- 部分一体机在 Android通道 设置 - 关于设备 中有 PC一键还原 或 Windows系统还原 等相关选项，弹出相关提示后点击确定即可自动恢复，下图为部分教学一体机的恢复选项图片：
> 创维Skyworth
> ![Skyworth](/images/Restore-System/skyworth.jpg)
>
> 海信Hisense
> ![Hisense](/images/Restore-System/Hisense.jpg)
>


- 部分一体机会在 Windows启动管理器 页面添加 一键还原、 Recovery 等相关字样，选择后会自动恢复系统

- 部分一体机会在BIOS启动时增加相关键盘按键操作选项，按下后会自动进行相关操作，下图为部分教学一体机的恢复键盘按键：

> 创维Skyworth
>![Skyworth](/images/Restore-System/skyworth_01.jpg)
>
> 鸿合HiteVision
>![HiteVision](/images/Restore-System/HiteVision_01.jpg)

#### 手动还原 再生龙CloneZilla 格式镜像
- 部分使用 再生龙CloneZilla 的机器可能无法使用/启动到自带的恢复工具，如果镜像文件完好无损，可以尝试参考该B站专栏的方法手动恢复：https://www.bilibili.com/opus/511922967402058685


### 希沃seewo
>[!TIP]
> 本文段教程适用于大部分希沃机型，部分可能存在差异，请以实际情况为准

- MT01 - MT11 为E盘下的隐藏文件夹下的GHO镜像文件 
- MT15 - MT2X 为E盘BACKUP_OS分区下的多个GHO文件
- 上面两个机型的OPS通常使用的是ghost工具进行恢复系统，镜像是gho形式，可以使用pe进行读取直接重装
- 希沃从MT4X开始使用 再生龙CloneZilla 作为一键恢复的程序，镜像文件无法被PE直接读取及使用，不同于之前的Ghost，再生龙支持UEFI/Legacy Boot引导，可以备份任何操作系统，其中包括Windows、UOS。

#### 通过Android系统恢复系统
- 此方法适用于部分设备

- 前往官网 https://www.seewo.com/support/customer/download?c=1#info ,找到 “PC一键还原”秘钥 然后点击下载，下载完成后打开压缩包，将“PCRecovery”文件复制到U盘根目录下
![图片](/images/Restore-System/seewo_01.png)

>[!NOTE]
> ⚠注意：U盘格式建议为FAT32，其他格式可能无法读取，如果U盘有多个分区，请复制到第一个分区

- 转到 Android 通道，打开设置，点击 关于设备 ，插入U盘，此时 PC一键还原 选项为可点击状态，点击后会弹出提示，点击确定，此时可将U盘拔出，OPS主机将自动重启，全程为自动操作，请耐心等待~~并坐和放宽~~即可

![图片](/images/Restore-System/seewo_1.jpg)

- 部分设备可能没有这个选项，可以尝试快速点击多次“触摸支持（支持 10 点触摸）”，会弹出“一键还原”的提示。

![图片](/images/Restore-System/seewo_001.png)

-----------
- 5代机以上操作方法：
- 在关机状态下，长按电源键不放（部分设备需要看到指示灯闪烁才能放开），直到出现下图中的界面

![图片](/images/Restore-System/seewo_2.jpg)

![图片](/images/Restore-System/seewo_3.jpg)

- 点击 系统恢复 ， 根据相关提示进行操作，然后耐心等待即可



#### 通过BIOS恢复系统

>[!TIP]
> 此方法适用于大部分设备，需要键盘操作

- 重启电脑，当出现 BIOS 按键 提示时，疯狂按下键盘上的 F2，直到出现BIOS界面
![图片](/images/Restore-System/seewo_4.jpg)

- 使用键盘上的 上下左右 方向键控制，转到 Advanced ，找到 OS backup and OS Recovery , 将 Disabled 改为 Enabled
![图片](/images/Restore-System/seewo_5.jpg)

- 按下 F10 保存，并选择Yes确定，或者按照下图中的步骤操作：
![图片](/images/Restore-System/seewo_6.jpg)

- 电脑重启，当出现 BIOS 按键 提示时，再次疯狂按下键盘上的 F2，直到出现BIOS界面
![图片](/images/Restore-System/seewo_7.jpg)

- 此时界面右边多出2个按键选项，F3是备份当前的系统，F4是还原原厂的系统，按下F4，出现相关提示，选择Yes确定即可，此时请耐心等待~~并坐和放宽~~，等待恢复完成
![图片](/images/Restore-System/seewo_8.jpg)

![图片](/images/Restore-System/seewo_9.jpg)

![图片](/images/Restore-System/Ghost_Recovery.jpg)

>[!NOTE]
> 部分型号的键盘操作按键不同，请以实际情况为准
>![图片](/images/Restore-System/seewo_02.jpg)
>


#### 其他
- MT15 \ MT23 的OPS机型会有一个恢复按钮，在关机状态下按住然后开机，等待出现Ghost恢复界面即可放开
![图片](/images/Restore-System/seewo_OPS.jpg)

- MT15 以下会在 Windows启动管理器 界面有一个 Onekey Recovery 选项，选择后会自动清空C盘并还原E盘下隐藏文件夹下的GHO镜像文件
![图片](/images/Restore-System/onekey.png)




## 使用PE进行操作

- 此方法适用于 无法使用/通过自带恢复工具、不想使用原厂系统等
> 准备工具:
> - 一个 ≧ 8GB 大小的U盘，**且没有重要资料文件**，以制作PE启动盘
> - 键盘，进PE的时候需要用到（没有键盘？ (。・∀・)ノ可以试试这个方法 在系统中设置以U盘启动：https://forum.smart-teach.cn/d/449-zai-bu-yong-jian-pan-de-qing-kuang-xia-qi-yong-pe） ~~不行的话还是老老实实带键盘吧~~
>
> -  Windows 镜像文件 (iso、wim、gho、esd等格式)

### 制作PE启动盘
> 本文章将使用FirPE作为演示，官网/下载：https://firpe.cn/page-247 ，也可以使用其他PE如 微PE 等，尽量避免使用流氓PE，如 大白菜、老毛桃 等

- 先查看FirPE官网帮助文档，在下面的操作中遇到一些问题也可以先查看此文档： https://docs.firpe.cn/guide/quickstart/

### 进入PE

- 下图为常用各主板启动快捷键，图片源自 https://zhuanlan.zhihu.com/p/572789021 ，仅供参考，可能会有所差异，请以实际情况为准：

![FirPE](/images/Restore-System/PE_01.jpg)

- 以希沃为例：开机后疯狂按下F7直到出现设备启动界面，选择你的U盘设备然后回车确定

![图片](/images/Restore-System/seewo_4.jpg)

![FirPE](/images/Restore-System/PE_04.png)

- 进入启动选项后，一般情况下选择 带 Windows 11 的字样的选项即可，然后等待进入到界面

### 安装系统

- 进入到PE桌面后，打开桌面上的 EasyRC一键装机 ，点击 选择镜像 ，找到存放镜像的文件位置并确定 (文件格式通常为 iso、wim、gho、esd 等格式)

![PE_seewo](/images/Restore-System/PE_1.jpg)

- 查看当前系统盘分区是为c盘还是d盘等（⚠注意：不是那个名称为 WinPE 的分区！！！），选择系统盘后，一般情况下，直接点击 开始安装 即可，安装时会格式化选择安装分区的内容，耐心等待安装完成，安装完成后会提示重启，你可以手动重启，或者10s后程序会自动重启

![PE_seewo](/images/Restore-System/PE_2.jpg)

![PE_seewo](/images/Restore-System/PE_3.jpg)

- 重启后继续等待，直至出现OOBE界面，按照页面说明操作即可


## 其他事项

- 如果使用Ghost还原是出现下面的图片中情况，请确保镜像文件完好无损，可以尝试使用PE进行安装

![fail](/images/Restore-System/fail_1.jpg)

![fail](/images/Restore-System/fail_2.jpg)


- 如果没有读到硬盘/只有U盘分区，或者出现了图下的情况，**如果您认为这超出了您的解决范围内，请不要继续操作设备，并及时与相关人员汇报**

![Fxxk_My_SSD_is_broke](/images/Restore-System/Fxxk_My_SSD_is_broke.jpg)