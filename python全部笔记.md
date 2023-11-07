# python全部笔记



## python基础编程语法

1. main.py打包成exe：
   
   >cmd输入main.py的路径，输入如下代码。
   Pyinstaller -F -w main.py



2. ==文件移动==：

   ```python
   import shutil
       for file in os.listdir(path):
           shutil.move(os.path.join(path, file), os.path.join(new_path, file))
   #  shutil函数第一个参数是旧的文件路径，第二个是新的文件的位置和新名称
   ```



3. ==文件重命名==：

   ```python
   os.rename(os.path.join(path, file), os.path.join(path, dic[file] + '.m4a'))
   #  原理就是join函数把路劲和文件名称连接，
   #  rename函数第一个参数是旧的文件路径，第二个是新的文件的位置和新名称
   ```



4. ==正则表达式（部分）==：
   找数字：data = re.findall('\\d+', file)  # 注意不能直接写成\d+，写成\\d+才规范
   找指定的特征:

   ```python
   data2 = re.findall(".*?<title>(.*?)_(.*?)_单曲在线试听_酷我音乐</title>", result3.text[0:250])
   #  rename函数第一个参数是需要正则匹配的.*?		第二个参数是对 哪个字符串 执行这样的查找操作
   
   """正则表达式匹配数字"""
   test_str = 'new12345号43了6667634'
   date = re.findall('.*?(\d+).*?', test_str)
   print(date)  # 结果等于['12345', '43', '6667634']
   
   """正则表达式匹配英文，写个+，如果有指定长度：把+换成{6}就是匹配6个长度"""
   # date = re.findall('.*?([a-zA-z]+).*?', test_str) 
   # 上面的就是所有的匹配都适用，固定长度的就额外写咯
   test_str = 'new12345号43了6667okmyyyx634'
   date = re.findall('.*?([a-zA-z]+).*?', test_str)
   print(date)  # 结果['new', 'okmyyyx']
   
   date = re.findall('.*?([a-zA-z]{3}).*?', test_str)
   print(date)  # 结果['new', 'okm', 'yyy']，多出来的不匹配
   ```



5. 批量创建文件夹：  # 总之里面必须是str，注意批量产生的文件夹只能在在.py同目录下

   ```py
   for i in range(2015, 2020):
       os.mkdir(str(i))  # 或者os.mkdir("第{}课".format(i))
   ```



6. pycharm中批量修改代码：

   > ctrl+shift+alt 双击选中，或者再加j全选（ctrl+shift+alt+j）全选

7. with open 将列表写入txt：
   ```py
   with open('由香.txt', 'w', encoding='utf-8') as f:
       for i in last_nums:
           f.write(i + '\n')
   ```

   

8. 列表太长怎么换行补充：在列表的末尾加个逗号，下一行补充''，即可
   ```py
   professional_name = ['jks', 'S1mple', 'Niko', 'm0nisy', 'huNter', 'stavn', 'Magisk', 'dupreeh', 'ELiGE',
            'ropz', 'electronic', 'device', 'ZywOo', 'Rain', 'KennyS', 'WDNMD']
   ```

   

9. if语句想着相反的走if语句：（在if后面加个not），例如：
   ```py
   if not os.path.exists(filename):
       os.mkdir(filename)
   ```

   

10. 清空列表：列表.clear

> 如有个列表list1 = ['a', 'b']
>
> 1. 删除整个列表：del list1
> 2. 删除指定的数据：del list1[0]  删除指定下标的元素（按索引删除元素）
> 3. 删除指定下标的元素，并返回这个值，如果没有指定，默认最后一个:list1.pop()或者list1.pop(1)
> 4. 移除某个元素：list1.remove('a')  只删第一个元素，后面如果还有可能删不掉
> 5. 清空整个列表：list1.clear()



11. 太长想换行写：
    空一格加个反斜杠\，如果是“”，那么第一行双引号结束后空加\然后下一行“。。。”\



12. set函数：把一个元素弄成无序不重复。（去重）



13. 随机数笔记：
    ```py
    test_random = random.randint(1, 20)  # 包含上下限的
    # 或者
    test2 = random.choice(list)  # 从列表中任挑一个元素。
    ```

    





14. enumerate() 函数：同时返回下标和该下标对应的数据

    ```python
    # 普通的for循环
    i = 0
    seq = ['one', 'two', 'three']
    for element in seq:
        print i, seq[i]
        i += 1
        
    # for循环使用enumerate
    seq = ['one', 'two', 'three']
    for i, element in enumerate(seq):
    	print i, element
    ```

    

    

15. range转列表：list1 = range(1,20)  \n  list2 = list(list1)  注意range是共有20个元素的，1是开始的数字。



16. list.index('test')  表示取得列表里test元素的索引下标



17. 修改变量名称在pycharm中，选中，按shift+F6



18. range笔记

```python
# 不写就默认为前两个
range(start, stop, step)

# 需要特别注意的是，倒着来的话还是很不一样的，倒着来开始就是最后一个减1，因为range包含前，不包含尾
# 倒着来：
range(len(list) - 1, -1, -1)  # 表示range(len(list))倒着来，【！步长必须是-1！】

for i in range(10, -1, -1):
    print(i)  # 结果为:10,9,……,1,0
```







## TKinter笔记

1. 想要标签居中：.grid(sticky=tk.N+tk.S)可以实现
   tk.Label(frame, text='制作日期：202306151530').grid(sticky=tk.N+tk.S)

2. 想要加个标签按钮是关于的（还未实现）：

```python
menu_tk = tk.Menu(root)  # 定义一个菜单栏
menu_tk.add_cascade(label="使用", command=page1.show_main)  # 在菜单栏上增加，菜单栏上的每个按钮甚至还可以展开追加的
menu_tk.add_cascade(label="帮助", command=show_help)
menu_tk.add_cascade(label="关于", command=show_about)
```



3. 登录页面后弹出新的页面：
   	自己总结：root在外面定义，所有的功能实现封装成类，具体实现再改为函数。
   ！！！且不同的页面建议新写一个py文件，再定义一个新的类calss balabala:\n
   具体教程：https://www.bilibili.com/video/BV1134y1B7bo/
   Tkinter 项目实战-学生信息管理系统，新手请绕道（面向对象&毕业设计&项目实战）

p3：09:00左右，具体时间戳：https://www.bilibili.com/video/BV1134y1B7bo?p=3&vd_source=084fc8785aec0ac1e1c664ac1bf2cc0d

销毁当前页面：（！！！！！！！！！！！超级无敌重要！！！）

```python
~page.destroy()
```



跳转页面的话就先上一行销毁第一面，再把新的类函数定义，把root放入函数的参数中
而且要在文件开头from （py文件 ） Import （calss类） 例如： from newpy import loginpage

文本框禁止输入状态：
    txt.config(state='disabled')  # 必须pack之后再disabled，这样就无法输入







## 打包exe

> cmd命令行打包基础指令

**不带控制台**
使用 pyinstaller -F 待打包文件名.py –noconsole（注意：noconsole前面必须是两个  -  -，一个 - 不起作用）

例子：
```linux
pip install pipenv
pipenv install
pipenv shell
pip install pandas
pip install pyinstaller
Pyinstaller --onefile main.py
```



**CET6打包程序的打包：**

```cmd
pipenv install
pipenv shell
pip install requests
Pyinstaller --onefile main.py
```



---



虚拟环境pyinstaller的教程：

> #建立虚拟环境
> pipenv install
> #进入虚拟环境（上一步可省略,因为没有虚拟环境的话会自动建立一个）
> pipenv shell
> #安装模块
> pip install requests pyquery pysimplegui fake_useragent
> #打包的模块也要安装
> pip install pyinstaller
> #开始打包
> pyinstaller -Fw E:\test\url_crawler.py
>
> Pyinstaller -F main.py 打包exe
>
> Pyinstaller -F -w main.py 不带控制台的打包
>
> Pyinstaller -F -w -i chengzi.ico main.py 打包指定exe图标打包
>
> Pyinstaller --onefile main.py 只生成1个文件
>
> 带图标：
> jpg转ico图标网址：https://www.zhihuilib.com/general/ico
> 打包自用图标命令：
>
> ```cmd
> PYinsinstaller -F -w -i kuwo.ico 酷我音乐.py
> ```
>
> 



参考网址：
巨齐全打包网址：
https://blog.csdn.net/qq_36807888/article/details/121220432?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168735525216782425131920%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168735525216782425131920&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-2-121220432-null-null.142

一般网址：
https://blog.csdn.net/qq_39241986/article/details/112791986?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522166843671116782391898530%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=166843671116782391898530&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-112791986-null-null.142



### conda创建虚拟环境打包

```cmd
# 暂时好像不咋行
conda create -n newinstall python==3.11

conda activate newinstall

conda list  # 查看以安装的库

```



## pycharm笔记

1. 把字母大写全部转换成小写：str1 = "LiBai is a boy"转成小写：str1.lower()  转成大写：str1.upper()

2. shift + alt + 小键盘的上或者下：表示快速将该行代码上移或者下移







## 典型、常用的python例子

1. 所有歌曲的改名把空格去掉

```python
    save_list1 = []
    for list1 in path_list1:
        for index, elements in enumerate(os.listdir(list1)):
            if ' ' in elements:
                new_file_name = elements.replace(' ', '')
                old_file_path = os.path.join(list1, elements)
                new_file_path = os.path.join(list1, new_file_name)
                os.rename(old_file_path, new_file_path)
```

