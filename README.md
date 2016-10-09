# ES2016_14353401
在安装Ubuntu时，选择的版本是Ubuntu16.04，所以在之后的一些安装上有些错误

1.在安装openjdk-7-jdk时，标准的命令是：
``` bash
	sudo apt-get install openjdk-7-jdk
```
但是在16.04版本中会出现错误：
	Packages “openjdk-7-jdk” has no installation condidate
 ![openjdk fail](C:\Users\Attenton\Desktop\openjdk fail.png)

说明16.04已经没有这个package，所以需要手动添加packages。

	sudo add-apt-repository ppa:openjdk-r/ppa
	sudo add-apt-repository ppa:webupd8team/java
	sudo apt-get update
之后就可以正常安装openjdk了。

之后就按照ppt给出的步骤执行，然后一切顺利，直到最后一步出现错误，给出的错误提示是：
```
	/home/attenton/dol/build/bin/main/runexample.xml:226: Execute failed: java.io.IOException: Cannot run program "/home/attenton/dol/build/bin/main/example1/HdS/src/sc_application": error=2, No such file or directory
```
没有找出之后查看了文件夹，发现是有这个文件的。在网上搜了一些问题，但都没有十分类似的问题和答案。后来发现，错误提示看的不完整，更前面还有一个提示：
```
<builtin>: recipe for target 'sc_application.o' failed
     [exec] g++: error: /include: No such file or directory
     [exec] make: *** [sc_application.o] Error 1
```
是g++执行时 /include文件出错，在google之后发现g++中的文件路径不能有空格，回到build_zip.xml中发现更改后的路径有换行，删除换行，从新编译之后build，就success了。

