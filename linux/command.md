## 文件信息

- `nm -D xxxx.so` 查看**动态库符号表** 
- `ar -t xxxx.a` 查看**静态库文件** 
- `ldd [执行程序/库文件]` 查看**依赖共享库**
- `fuser -v [文件/挂载点/网络端口]` 显示当前哪个进程正在使用目标

- linux选择多个文件/目录时可以用{a,b,c}格式，
  - `cp testa/{t1,t2,t3} testb`



## 软件包相关

- rpm包制作的 **spec文件** 中的%xxx是 **宏定义**，在/usr/lib/rpm/ 目录中的一些文件有定义，大多数在macros文件中

- fakeroot工具可以模拟root权限，配合alien工具可以将rpm包与deb包互相转换
  - `fakeroot alien [xxx.rpm/xxx.deb]`
