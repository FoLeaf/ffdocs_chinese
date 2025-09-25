# 配置选项

`ffconf.h` 文件定义了 FatFs 的许多配置选项。

### 功能配置
*   `FF_FS_READONLY`: 设置文件系统为只读。
*   `FF_FS_MINIMIZE`: 移除部分 API 函数以减小体积。
*   `FF_USE_FIND`: 启用 `f_findfirst` 和 `f_findnext`。
*   `FF_USE_MKFS`: 启用 `f_mkfs`。
*   `FF_USE_FASTSEEK`: 启用快速寻址功能。
*   `FF_USE_EXPAND`: 启用 `f_expand`。
*   `FF_USE_CHMOD`: 启用 `f_chmod` 和 `f_utime`。
*   `FF_USE_LABEL`: 启用 `f_getlabel` 和 `f_setlabel`。
*   `FF_USE_FORWARD`: 启用 `f_forward`。

### 命名空间与本地化
*   `FF_CODE_PAGE`: 指定 OEM 代码页。
*   `FF_USE_LFN`: 切换长文件名 (LFN) 支持。
*   `FF_MAX_LFN`: LFN 的最大长度。
*   `FF_LFN_UNICODE`: API 上的字符编码 (ANSI/OEM or Unicode)。
*   `FF_FS_RPATH`: 配置相对路径功能。

### 卷/驱动器配置
*   `FF_VOLUMES`: 要使用的卷（逻辑驱动器）的数量。
*   `FF_MULTI_PARTITION`: 切换多分区功能。
*   `FF_MIN_SS`, `FF_MAX_SS`: 定义扇区大小范围。
*   `FF_USE_TRIM`: 切换 ATA-TRIM 功能。

### 系统配置
*   `FF_FS_TINY`: 使用微型文件对象结构。
*   `FF_FS_EXFAT`: 切换 exFAT 支持。
*   `FF_FS_REENTRANT`: 切换线程安全。
*   `FF_FS_TIMEOUT`: 定义超时周期。

*(这是一个摘要。详细信息请参考原始文档。)*
