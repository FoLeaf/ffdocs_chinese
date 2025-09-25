## disk_status

disk_status 函数用于查询当前驱动器状态。

```c
DSTATUS disk_status (
  BYTE pdrv     /* [输入] 物理驱动器号 */
);
```

### 参数

*   **pdrv**: 用于标识目标设备的物理驱动器号。

### 返回值

返回当前驱动器状态标志的组合。
*   `STA_NOINIT`: 设备尚未初始化。
*   `STA_NODISK`: 驱动器中没有介质。
*   `STA_PROTECT`: 介质被写保护。

### 描述

此函数返回物理驱动器的状态。FatFs 模块仅引用 `STA_NOINIT` 和 `STA_PROTECT`。
