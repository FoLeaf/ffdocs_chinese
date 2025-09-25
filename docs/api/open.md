## f_open

f_open 函数用于打开一个文件。

```c
FRESULT f_open (
  FIL* fp,           /* [输出] 指向文件对象的指针 */
  const TCHAR* path, /* [输入] 文件名 */
  BYTE mode          /* [输入] 模式标志 */
);
```

### 参数

*   **fp**
    指向一个空白文件对象结构的指针。如果传入空指针，函数将失败并返回 `FR_INVALID_OBJECT`。

*   **path**
    指向一个以 null 结尾的字符串，该字符串指定了要打开或创建的[文件名](filename.md)。

*   **mode**
    模式标志，指定文件的访问类型和打开方法。

| 标志 | 含义 |
| --- | --- |
| `FA_READ` | 指定对文件的读访问。 |
| `FA_WRITE` | 指定对文件的写访问。 |
| `FA_OPEN_EXISTING` | 打开文件。如果文件不存在，函数将失败。(默认) |
| `FA_CREATE_ALWAYS` | 创建一个新文件。如果文件已存在，则截断并覆盖。 |
| `FA_CREATE_NEW` | 创建一个新文件。如果文件已存在，函数将失败。 |
| `FA_OPEN_ALWAYS` | 打开文件。如果文件不存在，则创建一个新文件。 |
| `FA_OPEN_APPEND` | 与 `FA_OPEN_ALWAYS` 相同，只是读/写指针被设置在文件的末尾。 |

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_FILE`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_DENIED`, `FR_EXIST`, `FR_INVALID_OBJECT`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_LOCKED`, `FR_NOT_ENOUGH_CORE`, `FR_TOO_MANY_OPEN_FILES`

### 描述

`f_open` 函数打开一个文件并创建一个文件对象。该对象是后续对文件进行读/写操作的标识符。文件访问会话结束后，应使用 `f_close` 函数关闭已打开的文件。

### 示例

```c
/* 读取一个文本文件并显示它 */

FATFS FatFs;   /* 逻辑驱动器的工作区 (文件系统对象) */

int main (void)
{
    FIL fil;        /* 文件对象 */
    char line[100]; /* 行缓冲区 */
    FRESULT fr;     /* FatFs 返回码 */


    /* 为默认驱动器提供一个工作区 */
    f_mount(&FatFs, "", 0);

    /* 打开一个文本文件 */
    fr = f_open(&fil, "message.txt", FA_READ);
    if (fr) return (int)fr;

    /* 逐行读取并显示 */
    while (f_gets(line, sizeof line, &fil)) {
        printf(line);
    }

    /* 关闭文件 */
    f_close(&fil);

    return 0;
}
```

### 相关参考

`f_read`, `f_write`, `f_close`, `FIL`, `FATFS`
