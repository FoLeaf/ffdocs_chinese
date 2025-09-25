## f_findnext

f_findnext 函数搜索下一个匹配的对象。

```c
FRESULT f_findnext (
  DIR* dp,              /* [输入] 指向目录对象的指针 */
  FILINFO* fno          /* [输出] 指向文件信息结构的指针 */
);
```

### 参数

*   **dp**: 指向由 `f_findfirst` 函数创建的有效目录对象的指针。
*   **fno**: 指向文件信息结构的指针，用于存储找到的目录项的信息。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

它从上一次调用 `f_findfirst` 或 `f_findnext` 函数的位置继续搜索。如果找到，对象的信息将存储到文件信息结构中。如果没有要读取的项目，则会在 `fno->fname[]` 中返回一个空字符串。

### 快速信息

当 `FF_USE_FIND == 1` 且 `FF_FS_MINIMIZE <= 1` 时可用。

### 相关参考

`f_findfirst`, `f_closedir`, `DIR`, `FILINFO`
