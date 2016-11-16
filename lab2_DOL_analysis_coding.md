####lab2.DOL实例分析&编程
#####1.修改example2，让3个square模块变成2个,
代码更改：
更改的是N的value，N的值代表迭代次数，如果要让square由3个更改为2个，square模块的代码不用发生变化，只需将square个数更改，那么就只需更改N的值，如下：

 ![code](C:\Users\Attenton\Desktop\code.png)
更改完代码之后在dol文件夹下执行命令进行编译：
```bash
sudo ant -f build_zip.xml all
```
之后在build/bin/main文件夹下运行程序：
```bash
sudo ant -f runexample -Dnumber=2
```
编译运行之后的结果:
 ![example1](C:\Users\Attenton\Desktop\example1.png)
显示的是0~19的4次方的得数。
dot图显示：
![dot](C:\Users\Attenton\Desktop\dot.png)
#####2.修改example1，使其输出3次方数
代码更改：
输出3次方，由于不是2的幂，所以只能更改square，使得输出为3次方数，修改如下所示：

 ![code1](C:\Users\Attenton\Desktop\code1.png)
更改完代码之后在dol文件夹下执行命令进行编译：
```bash
sudo ant -f build_zip.xml all
```
之后在build/bin/main文件夹下运行程序：
```bash
sudo ant -f runexample -Dnumber=2
```
运行结果如下，输出的是0~19的3次方：

 ![code1](C:\Users\Attenton\Desktop\code1.png)


