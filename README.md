# helloworld
测试用

#都读到


```r
setwd("D:/1桌面/学习/3.计算机/R语言/R语言应用课程/4第四次")
getwd()
Sys.time()
library(data.table)

#手动下载软件，导入数据
flights<-fread("flights14.csv")
flights

#返回数据集的维度信息
#第一维度（行数）代表数据集中的观测值数量。
#第二维度（列数）代表数据集中的变量（列）数量。
dim(flights)
```

文本缩进0.3

添加书签，选中文字，插入-书签-再次输入文字-添加

查找书签，插入-书签-选中文字-定位

> 之前word版本的存档和相关设置、探索

# 1.Introduction to data.table

## 1.1 Basics

### What is data.table?

data.table是一个R包，提供了data.frames的增强版本，这是用于以R进制存储数据的标准数据结构。在上面的数据部分中，我们已经使用fread（）创建了一个data.table。我们还可以使用data.table（）函数创建一个。这是一个例子：

```r
DT = data.table(
  ID = c("b","b","b","a","a","c"),
  a = 1:6,
  b = 7:12,
  c = 13:18
)

DT

class(DT$ID)
"character"
```

![image](assets/image-20241101015755-c6a0uzr.png)

您还可以使用`setDT（）`（对于data.frames和列表）和`as.data.table（）`（对于其他结构）将现有对象转换为data.table;差异超出了本小插曲的范围，?setDT和？as.data.table了解更多详细信息。

Note that:

* 与data.frames不同，默认情况下，字符类型character的列永远不会转换为因子factors。
* Row numbers are printed with a : in order to visually separate the row number from the first column.
* 当要打印的行数超过全局选项datatable.print.nrows（默认\= 100）时，它会自动仅打印顶部5行和底部5行（如数据部分所示）。如果您对data.frames有丰富的经验，那么您可能会发现自己在等待更大的表格打印和翻页，有时似乎是无休止的。You can query the default number like so:

```r
##用于获取R语言中data.table包的选项datatable.print.nrows的当前值
#最多显示100行
#超过100自动只打印前5行和后5行
getOption("datatable.print.nrows")
 
##可以将打印行数改为200行
options(datatable.print.nrows = 200)
getOption("datatable.print.nrows")
```

```r
print（hello world）
```


