## f_lseek

f_lseek 函数移动一个已打开文件对象的读/写指针。它也可以用来扩展文件大小（簇预分配）。

```c
FRESULT f_lseek (
  FIL*    fp,  /* [输入] 文件对象 */
  FSIZE_t ofs  /* [输入] 要设置的文件读/写指针偏移量 */
);
```

### 参数

*   **fp**: 指向已打开文件对象的指针。
*   **ofs**: 从文件顶部开始的字节偏移量，用于设置读/写指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

`f_lseek` 函数在不进行文件读/写操作的情况下移动文件读/写指针。当在写模式下指定一个超出文件大小的偏移量时，文件大小会在此函数中扩展到指定的偏移量。

如果需要为文件分配一个连续的数据区，请改用 `f_expand` 函数。

当 `FF_USE_FASTSEEK = 1` 时，快速寻址功能可用。通过使用内存中的簇链接映射表（CLMT）来实现快速的后向/长距离寻址操作。

### 示例

```c
/* 将读/写指针设置到 5000 */
res = f_lseek(fp, 5000);

/* 将读/写指针设置到文件末尾以追加数据 */
res = f_lseek(fp, f_size(fp));

/* 簇预分配 */
res = f_lseek(fp, PRE_SIZE);
```

### 相关参考

`f_open`, `f_truncate`, `f_expand`, `FIL`
