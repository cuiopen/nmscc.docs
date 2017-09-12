
# nms.io.Path

`path`为`unix`风格字符串，使用正斜杠`/`而不是反斜杠`\`。


path的前缀符有以下几种:

1. `#`
 程序目录， 即可执行程序所在目录的上一层。
 比如可执行程序是`c:/workspace/myapp/bin/test.exe`， 
 那么程序目录指的是`c:/workspace/myapp`，
 而`#/data/a.dat`指的是`c:/workspace/myapp/data/a.dat`。

2. `~`
 用户目录， Unix环境支持这个符号，没有做转换。
 在windows为环境变量`%USERPROFILE`，一般是`C:/Users/[username]`

path可以直接用字符串构造，也可以用format格式，比如
```c++
io::Path path1("#/data/file-0.dat");
io::path path2("#/data/file-{}.dat", 0);
```
这里path1和path2是相同的。
