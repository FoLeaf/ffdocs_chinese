## disk_ioctl

disk_ioctl 函数用于控制设备特定功能和除通用读/写之外的其他杂项功能。

```c
DRESULT disk_ioctl (
  BYTE pdrv,     /* [输入] 驱动器号 */
  BYTE cmd,      /* [输入] 控制命令代码 */
  void* buff     /* [输入/输出] 参数和数据缓冲区 */
);
```

### 参数

*   **pdrv**: 用于标识目标设备的物理驱动器号。
*   **cmd**: 命令代码。
*   **buff**: 指向依赖于命令代码的参数的指针。

### 返回值

`RES_OK`, `RES_ERROR`, `RES_PARERR`, `RES_NOTRDY`

### 描述

FatFs 模块仅需要以下设备无关的命令：
*   `CTRL_SYNC`: 完成挂起的写操作。
*   `GET_SECTOR_COUNT`: 检索驱动器上的扇区数。
*   `GET_SECTOR_SIZE`: 检索扇区大小。
*   `GET_BLOCK_SIZE`: 检索擦除块大小。
*   `CTRL_TRIM`: 通知设备可以擦除数据块。

### 快速信息

当 `FF_FS_READONLY == 1` 且 `FF_MAX_SS == FF_MIN_SS` 时，不需要 disk_ioctl 函数。
