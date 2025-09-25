## f_sync

f_sync 函数刷新正在写入的文件的缓存信息。

```c
FRESULT f_sync (
  FIL* fp     /* [输入] 文件对象 */
);
```

### 参数

*   **fp**: 指向要刷新的已打开文件对象的指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

`f_sync` 函数执行与 `f_close` 函数相同的过程，但文件保持打开状态，可以继续对文件进行读/写/寻址操作。这适用于长时间以写模式打开文件的应用程序，例如数据记录器。在一定间隔内执行 `f_sync` 函数可以最大限度地减少因突然断电、错误移除介质或不可恢复的磁盘错误而导致的数据丢失风险。

### 快速信息

当 `FF_FS_READONLY == 0` 时可用。

### 相关参考

`f_close`, [临界区](appnote.md#critical)
