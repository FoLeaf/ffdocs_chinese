## disk_read

disk_read 函数用于从存储设备读取数据。

```c
DRESULT disk_read (
  BYTE pdrv,     /* [输入] 物理驱动器号 */
  BYTE* buff,    /* [输出] 指向读取数据缓冲区的指针 */
  LBA_t sector,  /* [输入] 起始扇区号 */
  UINT count     /* [输入] 要读取的扇区数 */
);
```

### 参数

*   **pdrv**: 用于标识目标设备的物理驱动器号。
*   **buff**: 指向用于存储读取数据的字节数组的指针。
*   **sector**: LBA 中的起始扇区号。
*   **count**: 要读取的扇区数。

### 返回值

`RES_OK`, `RES_ERROR`, `RES_PARERR`, `RES_NOTRDY`

### 描述

此函数从物理驱动器读取一个或多个扇区。应用程序绝不能直接调用此函数。
