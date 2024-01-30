### 介绍

One-KVM是基于玩客云硬件和PiKVM软件的远控设备。通过移植PiKVM该软件至玩客云设备上，实现了极高的性价比，不到百元功能即可接近甚至超越部分昂贵的商业设备。

该设备在于帮助用户通过得到控制设备的HDMI 画面和鼠标键盘，去远程管理服务器、工作站或个人PC等。 和基于软件的远程管理方式不同，你无需在被控电脑安装任何软件，做到无侵入式控制。

该项目基于PiKVM和Fruity PiKVM，提供了玩客云兼容PiKVM操作的自动处理脚本。我不是PiKVM和Fruity PiKVM项目的开发者，所以不会对PiKVM软件本身和PiKVM deb包进行功能开发，请勿向此项目提交此类需求。

![image](https://github.com/mofeng-git/One-KVM/assets/62919083/ec7e049f-ca6c-426f-bfa4-314536965db0)

**功能特性**

![image](https://github.com/mofeng-git/One-KVM/assets/62919083/1e9305ee-fd9e-4e4c-ba25-141a924fef29)

### 快速开始

**方式一：直刷One-KVM镜像**

Releases带One-KVM前缀、burn后缀的为线刷镜像，可使用USB_Burning_Tool线刷至玩客云。镜像为开箱即用，刷好后启动设备就可以开始用One-KVM了。

**方式二：One-KVM脚本安装**

一键脚本适用于玩客云Armbian 22.11.0-trunk Jammy Linux onecloud 5.10.xxx(如5.10.149 5.10.158)镜像、作者发布地基础镜像。

```bash
git clone https://github.com/mofeng-git/One-KVM.git
cd One-KVM  && ./install.sh

#对于大陆网络环境，可以尝试使用下命令
wget https://mirror.ghproxy.com/https://github.com/mofeng-git/One-KVM/archive/refs/heads/main.zip -o One-KVM-main.zip && unzip One-KVM-main.zip
cd One-KVM-main  && ./install.sh
```
**方式三：docker镜像部署**

目前仅有pikvm-ch9329_amd64，后续将支持更多控制方式和处理器架构。
```bash
#使用示例：
docker run -itd -p443:443 -p80:80 --name pikvm-docker --device=/dev/ttyUSB0:/dev/kvmd-hid --device=/dev/video0:/dev/kvmd-video pikvm-ch9329:0.61
```

详细内容可以参照飞书文档：[One-KVM使用文档](https://p1b237lu9xm.feishu.cn/drive/folder/IsOifWmMKlzYpRdWfcocI7jdnQA?from=from_copylink)

### 其他

**感谢名单**

<details>

H_xiaoming

0蓝蓝0

fairybl

Will

浩龙

自.知

观棋不语٩ ི۶

以及各位讨论交流的网友
</details>

本项目间接或直接使用了下下列开源项目：
1. [pikvm/pikvm: Open and inexpensive DIY IP-KVM based on Raspberry Pi (github.com)](https://github.com/pikvm/pikvm)
2. [hzyitc/armbian-onecloud: Armbian for onecloud. 玩客云用armbian (github.com)](https://github.com/hzyitc/armbian-onecloud/)
3. [jacobbar/fruity-pikvm: Install Pi-KVM on debian SBCs such as Orange Pi, Banana Pi, Mango Pi, etc (github.com)](https://github.com/jacobbar/fruity-pikvm)

   

