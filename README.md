## 2051975 周煦松 多用户二级文件系统使用说明书
1. 运行server
- 进入FileSystem目录下
- 删除 myDisk.img 文件（用于检测虚拟磁盘初始化，可选）
- 在 FileSytem 目录下运行 `make`
- 在 MultiUser-secondFileSytem 目录下运行 `./FileSystem`
2. 运行client
- 在 Client 目录下运行 `make`
- 在 Client 目录下运行 `./Clinet 127.0.0.1 1235`
- 输入用户名
3. 用户端输入命令说明
- open(char *name, int mode) 打开文件
    - name: 打开文件路径名（相对路径） 
    - mode：读写权限 1-只读 2-只写 3-可读可写 
    - 返回值: 文件描述符
- close(int fd) 关闭文件
    - fd: 文件描述符
    - 返回值: -1-关闭失败 0-关闭成功
- read(int fd, int length) 从文件读取字符串
    - fd: 文件描述符
    - length: 读取字符长度
    - 返回值: 实际读取字符串长度
- write(int fd, char *buffer, int length) 写入文件
    - fd: 文件描述符
    - buffer: 写入的字符串
    - length: 写入的字符串长度
    - 返回值: 实际写入字符串长度
- seek(int fd, int position, int ptrname) 文件指针偏移
    - fd: 文件描述符
    - position: 偏移量
    - ptrname: 指针起始所在位置 0-从头偏移 1-从当前位置偏移 2-从末尾偏移
    - 返回值: 偏移后指针所在地址
- mkfile(char *name, int mode) 创建文件
    - name: 文件名
    - mode: 读写权限，同open当中的mode
- rm(char *name) 删除目录/文件
