## f_fdisk

f_fdisk 函数对物理驱动器进行分区。

```c
FRESULT f_fdisk (
  BYTE  pdrv,         /* [输入] 物理驱动器号 */
  const LBA_t ptbl[], /* [输入] 分区映射表 */
  void* work          /* [输入] 工作区 */
);
```

### 参数

*   **pdrv**: 指定要分区的物理驱动器。
*   **ptbl**: 要在驱动器上创建的分区大小列表。
*   **work**: 指向函数工作区的指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_NOT_READY`, `FR_WRITE_PROTECTED`, `FR_INVALID_PARAMETER`, `FR_NOT_ENOUGH_CORE`

### 描述

`f_fdisk` 函数在物理驱动器上创建 MBR 或 GPT 分区。分区映射表 `ptbl` 指定如何划分物理驱动器。

### 快速信息

当 `FF_FS_READOLNY == 0`、`FF_USE_MKFS == 1` 且 `FF_MULTI_PARTITION == 1` 时可用。

### 相关参考

[卷管理](filename.md#vol), `f_mkfs`
