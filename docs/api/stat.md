## f_stat

f_stat 函数检查文件或子目录是否存在。

```c
FRESULT f_stat (
  const TCHAR* path,  /* [输入] 对象名 */
  FILINFO* fno        /* [输出] FILINFO 结构 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要获取其信息的[对象](filename.md)。
*   **fno**: 指向空白 `FILINFO` 结构的指针，用于存储对象的信息。如果不需要此信息，请设置为空指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_FILE`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

`f_stat` 函数检查文件或子目录是否存在。如果不存在，函数返回 `FR_NO_FILE`。如果存在，函数返回 `FR_OK`，并且有关对象的信息（大小、时间戳和属性）将存储到文件信息结构中。

### 快速信息

当 `FF_FS_MINIMIZE == 0` 时可用。

### 示例

```c
FRESULT fr;
FILINFO fno;
const char *fname = "file.txt";

fr = f_stat(fname, &fno);
switch (fr) {
case FR_OK:
    printf("大小: %lu\n", fno.fsize);
    printf("时间戳: %u-%02u-%02u, %02u:%02u\n",
           (fno.fdate >> 9) + 1980, fno.fdate >> 5 & 15, fno.fdate & 31,
           fno.ftime >> 11, fno.ftime >> 5 & 63);
    printf("属性: %c%c%c%c%c\n",
           (fno.fattrib & AM_DIR) ? 'D' : '-',
           (fno.fattrib & AM_RDO) ? 'R' : '-',
           (fno.fattrib & AM_HID) ? 'H' : '-',
           (fno.fattrib & AM_SYS) ? 'S' : '-',
           (fno.fattrib & AM_ARC) ? 'A' : '-');
    break;
case FR_NO_FILE:
    printf("\"%s\" 不存在。\n", fname);
    break;
default:
    printf("发生错误。 (%d)\n", fr);
}
```

### 相关参考

`f_opendir`, `f_readdir`, `FILINFO`

```