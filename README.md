## 使用pickle序列化

<u>对象本质是“储存数据的内存块”</u>，把“内存块数据”保存到硬盘或者网络之间的传输，

需要对象“序列化和反序列化”

***序列化***：将对象转成串行化数据

***反序列化***：相反的过程，将读到的“串行化数据”转化成对象

```python
pickle.dump(obj,file)   #obj是需要被序列化的对象，file指的是储存文件
pickle.load(file)   #从file读取数据，反序列化成对象
#序列化和反序列化id不同是新的对象
```



## CSV文件操作

**与Excel文件不同：**

1. **值没有类型，所有值是字符串**
2. **不能指定字体颜色样式，单元格宽高，嵌入图表**
3. **没有多个工作表，不能合并单元格**

```python
import csv
with open("dd.csv","r") as f:
    a_csv=csv.reader(f)
    print(list(a_csv))
#------------------------------#
with open("dd.csv","w") as f:
    b_csv = csv.writer(f)
    b_csv.writerow(["id","姓名","年龄"])  #csv.writerow(["",""]) 写入列表到CSV
    b_list=[["1","陈一","1000"],["2","陈二","2000"],["3","陈三","3000"]]
    b_csv.writerows(b_list)  #写入二维多行列表
```

## OS和OS.path模块

**可以对操作系统进行操作，可以直接调用可执行文件、命令，直接操作文件、目录等**

### **os**模块

```python
import os

os.system("notepad.exe")  #打开记事本程序，调用系统软件
os.system("ping www.baidu.com")  #执行cmd命令
os.startfile("D:\下载\微信绿化版\WeChat\WeChat.exe")  #直接调用可执行文件
os.remove(path)  #删除指定文件
os.raname(oldname,newname)  #重命名文件或目录
os.stat(path)  #返回文件所有属性
os.listdir(path)  #返回path目录下的文件和目录列表
os.mkdir(path)  #创建一个目录
os.makedirs(path1/path2/path3····)  #创建多级目录
os.rmdir(path)  #删除目录
removedirs(path1/path2/path3····)  #删除多级目录
os.getcwd()  #返回当前工作目录
os.chdir(path)  #把path设置为当前工作目录
os.walk()  #遍历目录树
print(os.name)  #获取当前系统  windows返回nt linux和unix返回posix 
print(os.sep)  #获取系统分隔符 windows返回\ linux和unix返回/
print(repr(os.linesep))  #获取系统换行符 windows返回\r\n linux和unix返回\n\
#将对象转换为字符串，遵守Python协议 __repr__

```

### os.path

![image-20210603173943603](https://typora-1300671906.cos.ap-nanjing.myqcloud.com/img/image-20210603173943603.png)

