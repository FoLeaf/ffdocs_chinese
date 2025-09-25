## f_mount

f_mount 函数为 FatFs 模块提供工作区。

```c
FRESULT f_mount (
  FATFS*       fs,    /* [输入] 文件系统对象 */
  const TCHAR* path,  /* [输入] 逻辑驱动器号 */
  BYTE         opt    /* [输入] 初始化选项 */
);
```

### 参数

*   **fs**: 指向要注册和清除的文件系统对象的指针。空指针将注销已注册的文件系统对象。
*   **path**: 指向一个以 null 结尾的字符串，该字符串指定逻辑驱动器。
*   **opt**: 挂载选项。0: 延迟挂载, 1: 立即挂载。

### 返回值

`FR_OK`, `FR_INVALID_DRIVE`, `FR_DISK_ERR`, `FR_NOT_READY`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`

### 描述

在执行文件/目录操作之前，需要使用 `f_mount` 函数为逻辑驱动器注册一个文件系统对象。如果未指定强制挂载 (`opt = 0`)，则无论物理驱动器状态如何，此函数始终成功（延迟挂载）。

### 快速信息

始终可用。

### 相关参考

`f_open`, `FATFS`
