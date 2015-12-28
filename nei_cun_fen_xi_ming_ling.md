# 内存分析命令

jinfo:

```
查看Java进程的栈空间大小:sudo -u tomcat /home/java/default/bin/jinfo - ThreadStackSize 14750
查看是否使用了压缩指针:sudo -u tomcat /home/java/default/bin/jinfo -flag UseCompressedOops 14750
查看系统属性:sudo -u tomcat /home/java/default/bin/jinfo -sysprops 14750
```

jstack:
```
查看一个指定的Java进程中的线程的状态:sudo -u tomcat /home/java/default/bin/jstack 14750
```
jstat:

```
查看gc的信息:sudo -u tomcat /home/java/default/bin/jstat -gcutil 14750
```
jmap&mat

```
空间中各个年龄段的空间的使用情况:sudo -u tomcat /home/java/default/bin/jmap -heap 14750
jmap指定的dump文件一定要是tomcat用户可写，比如可以新创建一个文件夹
sudo mkdir /home/memdump
sudo chown tomcat:tomcat /home/memdump
sudo -u tomcat /home/java/default/bin/jmap -dump:live,format=b,file=/home/memdump/memMap.20131125.hprof 14750
```
（转载本站文章请注明作者和出处 JavaRanger – javaranger.com ，请勿用于任何商业用途）

本文链接: http://www.javaranger.com/archives/1063 