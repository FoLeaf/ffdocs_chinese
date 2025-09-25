## f_setlabel

f_setlabel 函数设置/删除卷的标签。

```c
FRESULT f_setlabel (
  const TCHAR* label  /* [输入] 要设置的卷标 */
);
```

### 参数

*   **label**: 指向一个以 null 结尾的字符串，该字符串指定要设置的卷标。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_INVALID_NAME`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`

### 描述

当字符串带有驱动器前缀时，卷标将设置到由驱动器前缀指定的卷。如果未指定驱动器号，则卷标将设置到默认驱动器。如果给定的卷标长度为零，则将删除卷上的卷标。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_USE_LABEL == 1` 时可用。

### 相关参考

`f_getlabel`
