## disk_initialize

disk_initialize 函数用于初始化存储设备。

```c
DSTATUS disk_initialize (
  BYTE pdrv           /* [输入] 物理驱动器号 */
);
```

### 参数

*   **pdrv**: 用于标识目标设备的物理驱动器号。

### 返回值

此函数返回当前驱动器状态标志作为结果。

### 描述

此函数初始化存储设备，使其准备好进行通用的读/写操作。应用程序在使用 FatFs 期间绝不能调用此函数。
