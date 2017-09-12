
# nms.io.File

## 1. 读文件
下面的示例，从文件中读取float型数组
```c++

u64 readFile(const io::Path& path, float buffer[]) {
    using namespace io;

    //1. 只读方式打开文件
    File file(path, File::Read);

    //2. 取得文件长度
    const auto file_len = file.size();

    //3. 计算有多少个元素
    const auto cnts     = file_len / sizeof(float);

    //3. 读文件 [注意这里是元素数，而不是字节长]
    const auto read_len = file.read(buffer, cnts);

    // 4. 返回读取个数
    return read_len;
}

```

## 2. 写文件
下面的示例，把float型数组写入到文件中

```c++
u64 writeFile(const io::Path& path, float buffer[], u64 buff_len) {
    using namespace io;

    //1. 可写方式打开文件
    File file(path, File::Write);

    //2. 写文件 [注意这里是元素数，而不是字节长]
    const auto write_len = file.read(buffer, buffer_len);

    // 4. 返回写入个数
    return write_len;
}

```
