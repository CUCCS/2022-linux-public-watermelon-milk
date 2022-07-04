# 实验4

## 实验环境

`Ubuntu 20.04 Server 64bit`

`Vscode`

### 实验任务

#### 用bash编写一个图片批处理脚本，实现以下功能

 ☑支持命令行参数方式使用不同功能

 ☑支持对指定目录下所有支持格式的图片文件进行批处理指定目录进行批处理

 ☑支持以下常见图片批处理功能的单独使用或组合使用

 ☑支持对`jpeg`格式图片进行图片质量压缩

 ☑支持对`jpeg/png/svg`格式图片在保持原始宽高比的前提下压缩分辨率

 ☑支持对图片批量添加自定义文本水印

 ☑支持批量重命名（统一添加文件名前缀或后缀，不影响原始文件扩展名）

 ☑支持将`png/svg`图片统一转换为jpg格式

#### 用bash编写一个文本批处理脚本， 对以下附件分别进行批量处理完成相应的数据统计任务

 ☑统计不同年龄区间范围（20岁以下、[20-30]、30岁以上）的球员数量、百分比

 ☑统计不同场上位置的球员数量、百分比

 ☑名字最长的球员是谁？名字最短的球员是谁？

 ☑年龄最大的球员是谁？年龄最小的球员是谁？

#### 用bash编写一个文本批处理脚本，对以下附件分别进行批量处理完成相应的数据统计任务

 ☑统计访问来源主机TOP 100和分别对应出现的总次数

 ☑统计访问来源主机TOP 100 `IP`和分别对应出现的总次数

 ☑统计最频繁被访问的`URL` TOP 100

 ☑统计不同响应状态码的出现次数和对应百分比

 ☑分别统计不同4XX状态码对应的TOP 10 `URL`和对应出现的总次数

 ☑给定URL输出TOP 100访问来源主机

#### 实验要求

 继承第一章

 所有源代码文件必须单独提交并提供详细的`-help`脚本内置帮助信息

 任务二的所有统计数据结果要求写入独立实验报告

#### 任务1

 1.安装`imagemagick`

 `sudo apt-get update`

 `sudo apt-get install imagemagick`

 2.编写[task1.sh](code/task1.sh)

 3.执行效果如下：

 `echo -h`   
 ![echo-h](img/echo-h.png)

 `echo -R`     
 ![echo-R](img/echo-R.png)

 `echo -r 50`     
 ![echo_r](img/echo_r.png)

 `echo -a 50 lan`    
 ![水印](img/echo-a.png)

 `echo -add_1 A`    

 `echo -add_2 a`    
 ![前缀名和后缀名](img/echo-add.png)

 `echo -c`   
 ![修改类型](img/echo-c.png)

### 任务2-1

 编写[task2-1.sh](code/task2-1.sh)

 ![-h](img/ts2-1-h.png)   

 查看[task2-1最终结果](task2-1_result.md)

<br/> 

### 任务2-2

 编写[task2-2.sh](code/task2-2.sh)

 ![-h](img/ts2-2-h.png) 

 查看[task2-2最终结果](task2-2_result.md)