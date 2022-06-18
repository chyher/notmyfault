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

## fuser 
- 可以显示出当前哪个[程序]在使用磁盘上的某个[文件/挂载点/网络端口]，并给出程序进程的详细信息。

## 使用find命令时可以指定时间戳相关属性，文件的时间戳可以使用stat [filename]查询
- find -[atime/amin] 指定最近一次访问时间对应Access
- find -[mtime/mmin] 指定最近一次内容修改时间对应Modify
- find -[ctime/cmin] 指定最近一次属性修改时间对应Change
- 例：find -cmin +30 查找在30min时间内没有访问过的文件（-30即访问过的文件）
