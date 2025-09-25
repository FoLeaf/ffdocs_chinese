## f_chmod

f_chmod 函数更改文件或子目录的属性。

```c
FRESULT f_chmod (
  const TCHAR* path, /* [输入] 对象名 */
  BYTE attr,         /* [输入] 属性标志 */
  BYTE mask          /* [输入] 属性掩码 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要更改的对象。
*   **attr**: 要设置的属性标志 (`AM_RDO`, `AM_ARC`, `AM_SYS`, `AM_HID`)。
*   **mask**: 属性掩码，指定要更改哪个属性。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_FILE`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

`f_chmod` 函数更改文件或子目录的属性。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_USE_CHMOD == 1` 时可用。
