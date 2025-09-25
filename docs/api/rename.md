## f_rename

f_rename 函数重命名和/或移动文件或子目录。

```c
FRESULT f_rename (
  const TCHAR* old_name, /* [输入] 旧对象名 */
  const TCHAR* new_name  /* [输入] 新对象名 */
);
```

### 参数

*   **old_name**: 指向一个以 null 结尾的字符串，该字符串指定要重命名的现有[文件或子目录](filename.md)。
*   **new_name**: 指向一个以 null 结尾的字符串，该字符串指定新的对象名。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_FILE`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_EXIST`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_LOCKED`, `FR_NOT_ENOUGH_CORE`

### 描述

重命名文件或子目录，也可以将其移动到同一卷中的另一个目录。要重命名的文件不能是打开的文件。

*备注：移动子目录时要小心。子目录不能移动到其自身或其任何子目录中，否则移动的子目录将丢失。*

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_FS_MINIMIZE == 0` 时可用。

### 示例

```c
/* 在默认驱动器中重命名一个对象 */
f_rename("oldname.txt", "newname.txt");

/* 重命名一个对象并将其移动到驱动器中的另一个目录 */
f_rename("log.txt", "old/log0001.txt");
```

### 相关参考

`f_unlink`, `f_mkdir`
