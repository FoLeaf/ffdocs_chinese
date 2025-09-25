## disk_write

disk_write 函数用于向存储设备写入数据。

```c
DRESULT disk_write (
  BYTE pdrv,        /* [输入] 物理驱动器号 */
  const BYTE* buff, /* [输入] 指向要写入的数据的指针 */
  LBA_t sector,     /* [输入] 要开始写入的扇区号 */
  UINT count        /* [输入] 要写入的扇区数 */
);
```

### 参数

*   **pdrv**: 用于标识目标设备的物理驱动器号。
*   **buff**: 指向要写入的字节数组的指针。
*   **sector**: LBA 中的起始扇区号。
*   **count**: 要写入的扇区数。

### 返回值

`RES_OK`, `RES_ERROR`, `RES_WRPRT`, `RES_PARERR`, `RES_NOTRDY`

### 描述

此函数将一个或多个扇区写入物理驱动器。应用程序绝不能直接调用此函数。

### 快速信息

当 `FF_FS_READONLY == 1` 时，此函数不是必需的。
