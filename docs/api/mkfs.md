## f_mkfs

f_mkfs 函数在逻辑驱动器上创建一个 FAT/exFAT 卷。

```c
FRESULT f_mkfs (
  const TCHAR* path,   /* [输入] 逻辑驱动器号 */
  const MKFS_PARM* opt,/* [输入] 格式化选项 */
  void* work,          /* [-]  工作缓冲区 */
  UINT len             /* [输入] 工作缓冲区大小 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要格式化的逻辑驱动器。
*   **opt**: 指定格式化选项结构 `MKFS_PARM`。如果为 NULL，则使用默认值。
*   **work**: 指向用于格式化过程的工作缓冲区的指针。
*   **len**: 工作缓冲区的大小，以字节为单位。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_NOT_READY`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_MKFS_ABORTED`, `FR_INVALID_PARAMETER`, `FR_NOT_ENOUGH_CORE`

### 描述

此函数用于在逻辑驱动器上创建文件系统。`opt` 参数可以控制 FAT 类型、FAT 副本数、对齐方式、根目录条目数和簇大小。

### 快速信息

当 `FF_FS_READOLNY == 0` 且 `FF_USE_MKFS == 1` 时可用。

### 相关参考

[卷管理](filename.md#vol), `f_fdisk`
