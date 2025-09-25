## f_closedir

f_closedir 函数关闭一个已打开的目录。

```c
FRESULT f_closedir (
  DIR* dp     /* [输入] 指向目录对象的指针 */
);
```

### 参数

*   **dp**: 指向要关闭的已打开目录对象结构的指针。

### 返回值

`FR_OK`, `FR_INT_ERR`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

`f_closedir` 函数关闭一个已打开的目录对象。函数成功后，该目录对象将不再有效，可以被丢弃。

### 快速信息

当 `FF_FS_MINIMIZE <= 1` 时可用。

### 相关参考

`f_opendir`, `f_readdir`, `DIR`
