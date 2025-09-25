## f_expand

f_expand 函数为文件准备或分配一个连续的数据区。

```c
FRESULT f_expand (
  FIL*    fp,  /* [输入] 文件对象 */
  FSIZE_t fsz, /* [输入] 要扩展到的文件大小 */
  BYTE    opt  /* [输入] 分配模式 */
);
```

### 参数

*   **fp**: 指向已打开文件对象的指针。
*   **fsz**: 要为文件准备或分配的大小（以字节为单位）。
*   **opt**: 分配模式。准备分配 (0) 或立即分配 (1)。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_INVALID_OBJECT`, `FR_DENIED`, `FR_TIMEOUT`

### 描述

`f_expand` 函数为文件准备或分配一个连续的数据区。当 `opt` 为 1 时，数据区在此函数中被分配给文件。当 `opt` 为 0 时，函数会找到一个连续的数据区，并将其设置为下一次分配的建议点。

### 快速信息

当 `FF_USE_EXPAND == 1` 且 `FF_FS_READONLY == 0` 时可用。

### 相关参考

`f_open`, `f_lseek`, `FIL`
