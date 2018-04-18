# kvm-devops
* 虚拟化简史

![](https://images0.cnblogs.com/blog2015/697113/201506/051254593325048.jpg)

* KVM

```
全称：Kernel-based Virtual Machine
软件性质：开源
开发人员：Red Hat
操作系统内核：Linux 2.6.20
硬件架构：x86
```

```
KVM 是基于虚拟化扩展（Intel VT 或者 AMD-V）的 X86 硬件的开源的 Linux 原生的全虚拟化解决方案。
KVM 中，虚拟机被实现为常规的 Linux 进程，由标准 Linux 调度程序进行调度；虚机的每个虚拟 CPU 被实现为一个常规的 Linux 线程。这使得 KMV 能够使用 Linux 内核的已有功能。
KVM 本身不执行任何硬件模拟，需要用户空间程序通过 /dev/kvm 字符设备设置一个客户机虚拟服务器的地址空间，向它提供模拟 I/O，并将它的视频显示映射回宿主的显示屏。目前这个应用程序是 QEMU。
```

![](https://images0.cnblogs.com/blog2015/697113/201505/311544349234041.jpg)

```
Guest：客户机系统，包括CPU（vCPU）、内存、驱动（Console、网卡、I/O 设备驱动等），被 KVM 置于一种受限制的 CPU 模式下运行。
KVM：运行在内核空间，提供 CPU 和内存的虚级化，以及客户机的 I/O 拦截。Guest 的 I/O 被 KVM 拦截后，交给 QEMU 处理。
QEMU：修改过的被 KVM 虚机使用的 QEMU 代码，运行在用户空间，提供硬件 I/O 虚拟化，通过 IOCTL /dev/kvm 设备和 KVM 交互。
```

* QEMU

```
KVM uses QEMU for I/O hardware emulation.
```

* libvirt

```
KVM is managed via the libvirt API and tools.
```

* tools

```

virsh ：基于 libvirt 的命令行工具
virt-install：创建 KVM 虚机命令工具
```

---
---
OS：CentOS Linux release 7.3.1611 (Core)

* 安装

```
yum install qemu-kvm libvirt libvirt-python libguestfs-tools virt-install
```
* 配置

```

```

* 启动

```
systemctl enable libvirtd && systemctl start libvirtd

```

* 使用



