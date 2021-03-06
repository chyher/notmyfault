# 虚拟机环境构建

- 可选择下载 VMware / Virtual box 等虚拟机软件

- 启动虚拟机前请确保电脑以开启虚拟化使能
  - 进入bios界面
    - 若为intel，则将 **intel virtual technology** 使能
    - 若为amd，则将 **SVM** 使能

## centos7

该教程以经典centos7 minimal版本为例

- 进入centos官网，选择DOWNLOAD
- 随便找一个镜像站点（可将站点centos版本号改为7，安装经典的centos7稳定版）
- 由于该教程以学习为目的，故下载minimal-iso最小镜像
- 将下载的iso导入虚拟机，并启动安装，做一些图形的初始化配置
- 进入虚拟机后查看网络是否连通
  - `ip addr` 查看是否有ip地址
  - `ping [可连通的网站]` 查看能否ping通
  - 若不能连通，则配置一下网卡
    - `vi /etc/sysconfig/network-scripts/ifcfg-网卡名`
    - 把ONBOOT=no，改为ONBOOT=yes

- 安装常用软件
  - `yum install -y net-tools wget telnet-server.x86_64 telnet.x86-64 gcc-c++ lsof`

## 虚拟机网络
- net模式为虚拟机连接至主机vmnet8，此时虚拟机可以ping通主机但主机无法ping虚拟机，此时可以使用端口转发的方式，配置主机的某一端口为映射至虚拟机的某一端口，配置转发的虚拟虚拟机ip。重启虚拟机后即可进行端口转发，如映射至虚拟机22端口即可使用ssh服务(虚拟机未修改22端口时)
