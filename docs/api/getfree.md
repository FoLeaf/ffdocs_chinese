## f_getfree

f_getfree 函数获取卷上的空闲簇数。

```c
FRESULT f_getfree (
  const TCHAR* path,  /* [输入] 逻辑驱动器号 */
  DWORD* nclst,       /* [输出] 空闲簇数 */
  FATFS** fatfs       /* [输出] 对应的文件系统对象 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定逻辑驱动器。
*   **nclst**: 指向 `DWORD` 变量的指针，用于存储空闲簇数。
*   **fatfs**: 指向指针的指针，用于存储指向相应文件系统对象的指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`

### 描述

`f_getfree` 函数获取卷上的空闲簇数。可以利用此信息计算出以扇区为单位的可用空间。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_FS_MINIMIZE == 0` 时可用。

### 相关参考

`FATFS`
