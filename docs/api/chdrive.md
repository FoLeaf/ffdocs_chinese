## f_chdrive

f_chdrive 函数更改当前驱动器。

```c
FRESULT f_chdrive (
  const TCHAR* path  /* [输入] 逻辑驱动器号 */
);
```

### 参数

*   **path**: 指定要设置为当前驱动器的逻辑驱动器号。

### 返回值

`FR_OK`, `FR_INVALID_DRIVE`

### 描述

`f_chdrive` 函数仅更改当前驱动器。当前驱动器号的初始值为 0。

### 快速信息

当 `FF_FS_RPATH >= 1` 时可用。

### 相关参考

`f_chdir`, `f_getcwd`
