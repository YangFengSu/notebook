## 笔记总结 

1. 添加###几个井号就是几级标题，通常只支持6个

2. 大于号后面接的内容就是引用部分，想要取消引用则回车两次（==所有的都是==）

3. 短横杆再空格生成无序列表；数字加一点再空格可以生成有序列表

4. **<u>任务列表</u>**横杆，空格，方括号，空格，方括号。空格里面输入x表示已完成，当然也可以自己打钩

   > *-* [  ,然后再接回来]

5. 左右各一个星号*是斜体

​		左右各两个星号*是加粗。

5. 左右两条波浪线就变成删除

​		左右两个等号就是高亮

​		下划线是html中的u标签：<u></u>,在两个大小号间添加需要下划线的文字

​		表情是冒号，加表情名称，加冒号:smile,(这里记得把冒号加两边才有表情) 写出来就会发现有提示的

6. 三条短横杆再回车是分割线

7. 代码块：三个波浪号，加上语言，比如c或者python

8. 表格：分为3部分(这里表格部分不太清楚的，可能后续需要更新笔记)
   1. 表头|姓名|年龄|成绩|。注意中间只有一个英文竖线划分
   2. 对其方式|：---|：---：|---：|，左边冒号左对齐，两边都有就居中
   3. 接着下面就输入表格

9. 行内代码（不咋熟悉，好像不太对劲）：~print(x) ~ 

10. 行内数学公式，两个美元符号中间添加公式

11. > <u>html添加视频的语法为：</u>
    >
    > ==从这里也可以看出想要不显示html可以有种方法就是把html代码加粗或者其他方式==
    >
    > **<video width="880" height="460" controls> <source src="D:\Lenovo\下载\Video\KDD22-fp0643.mp" type="video/mp4"> Your browser does not support the video tag. </video>**

超链接语法：需要所有符号都是英文状态下 【标题】(链接)  

12. 把字体变大完全是html的语法

    > <font size=8></font>	在><这中间添加需要变大字号的文字

感觉还不错的markdown笔记记录博客：[markdown笔记]([【精选】【MarkDown】——MarkDown学习笔记_markdown笔记-CSDN博客](https://blog.csdn.net/qq_50497708/article/details/126563278?ops_request_misc=%7B%22request%5Fid%22%3A%22169875007916800197086912%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=169875007916800197086912&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-126563278-null-null.142^v96^pc_search_result_base8&utm_term=markdown笔记&spm=1018.2226.3001.4449))

13. 字号设置

> <font size=7></font>
>
> 在><中间填入想要增大字号的文字





## 下面是上面笔记的练习

---

---

---



> 这里是一段引用

- 无序列表1
- 无序列表2

1. 有序列表1
2. 有序列表2

- [x] 任务列表1

- [ ] 任务列表2



*斜体*		**加粗**	==高亮== 	~~删除~~ 	<u>下划线</u>	

~~~python
print(test)
def my_main():
    print('Yes!')
    return 0
~~~



表格示例：(写的时候估计是输不了|:---:|了，但是选择下面查看代码模式，就可以看到是能有居中的代码部分的)

|    name     | age          | score       |
| :---------: | ------------ | ----------- |
| \|:---\\\\| | \|:---:\\\\| | \|---:\\\\| |

行内数学公式：$\alpha=x^2$ 

最后一步，视频分享链接

试着添加本地视频文件：

D:\Lenovo\下载\Video\KDD22-fp0643.mp4

<video width="800" height="460" controls>
    <source src="D:\Lenovo\下载\Video\KDD22-fp0643.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>




