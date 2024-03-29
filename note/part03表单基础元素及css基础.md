# 一、复习
1. WEB的组成
    - 结构 html，网页的内容，比如文本、图片...
    - 表现 css，网页的样式
    - 行为 js，网页的交互
2. 文件命名规范
    - 数字、字母、下划线组成
    - 不能用中文
    - 不能以数字开头
    - 语义化命名
    - 驼峰式命名
3. 项目文件夹组成
    - css文件夹、js文件夹、images文件夹、多个html文件
4. 标签语法
    - 单 <标签名 属性=“值” 属性=“值”>
    - 双 <标签名 属性=“值” 属性=“值”> 内容 </标签名>
5. 常用标签，至少10个
    - h1~h6,strong,b,em,i,u,del,s,sup,sub,p
    - br,hr
6. 特殊符号，至少5个
    &gt; &lt; &nbsp; &yen; &copy; &reg; &trade; &times; &divide;
7. 列表标签，三类
    - 有序 <ol>  <li></li><li></li>   </ol>
    - 无序 <ul>  <li></li><li></li>   </ul>
    - 定义 <dl>  <dt></dt> <dd></dd>  </dl>
8. 图片标签及标签属性
    <img src="图片路径" alt="替换文本"  title="悬浮框" width="宽" height="高">
9. 链接标签及标签属性
    <a href="链接目标" target="何处打开链接"></a>
10. html、xhtml和html5的区别
    - html 超文本标记语言
    - xhtml 可扩展的超文本标记语言，语法更加严格
    - html5 html的第五个版本
11. 姓名

# 二、表单
1. 作用：适用于收集数据信息

2. <form></form> 定义表单，双标签
    - action="跳转地址"
    - target=“控制打开方式”
        - _self 当前窗口打开
        - _blank 新选项卡打开

3. <input type="" value=""> 表单控件
    - type 控件类型
        - text 单行输入框控件
        - password 密码
        - submit 提交按钮，配合form标签中的action进行跳转使用
        - reset 重置按钮，清空之前中输入框内的数据
        - button 普通按钮，什么作用都没有
    - value 默认值

# 三、css基本语法
1. css语法：
    - css属性:值;
    - cascading style sheet 层叠样式表

2. 行内样式表（使用少）
    - 行内样式表修饰的是对应自己的这个标签
    - 写在开始标签里
    - 语法：
        - style=" css属性:值; css属性:值; ... "

3. 内部样式表（使用少）
    - style标签一般放到head里面
    - 语法：
        <style>
            选择器{
                css属性:值;
            }
        </style>

4. 外部样式表-创建（经常用）
    - 所有的css语句放在以.css为扩展名的文件中
    - .css内部的语法：
        选择器{
            css属性:值;
        }
    - 必须通过link标签引入
        - link 单标签
        - rel="stylesheet" 当前文件与href指定的文件关系是样式表
        - href="css文件路径"

5. 外部样式表-导入
    - 语法
        @import url(css路径);
    - link和@import的区别：
        - 差别一：本质的差别：
            - link属于xhtml标签，@import是css提供的一种方式
        - 差别二：加载顺序的差别
            - 当一个页面被加载时，link引用的css会同时被加载，而@import引用的css会等到页面全部下载完成后再加载，所以有时候浏览@import加载css的页面开始会没有样式  
        - 差别三：兼容的差别
            - @import是css2.1提出的，只有在IE5以上才能识别，而link标签没有这个问题
        - 差别四：使用dom控制样式的差别
            - 当使用js的dom去改变样式的时候，只能使用link标签，因为@import不是dom可以控制的

# 四、样式表的优先级
1. 多个样式表修饰同一个元素
    - !important > 行内样式 > 内部样式/外部样式
    - !important 写在属性值后面，分号前面
    - 若优先级一致，对同一个元素进行重复修饰时，执行后者

# 五、选择器
1. 什么是选择器
    - 查找页面元素的一种方法

2. 学习很多选择器的原因
    - 为了提高查找元素的精准度

3. 标签选择器
    - 通过标签的名字来查找页面中的元素，只要是对应的标签名都可以执行
    - 语法
        - 标签名{ }

4. 类选择器
    - 通过给元素起一个类名，在css内用类名去查找页面中的元素
    - 语法
        - HTML部分 <div class="demo"></div>
        - CSS部分 .demo{ }
    - 多个类
        - 多个类名共用一个class属性，多个类名之间用空格隔开
        - 多个类名同时使用语法：
            - HTML部分 <div class="demo box"></div>
            - CSS部分 .demo.box{ }

5. ID选择器
    - 给元素起id名字，在css内通过id的名字去查找页面中的元素
    - id名不能重复，具有唯一性
    - 语法
        - HTML部分 <div id="demo"></div>
        - CSS部分 #demo{ }

6. 通配符选择器
    - 能够匹配页面中所有的元素，通常用于取消元素自带的外边距和内边距
    - 语法
        - *{ }

7. 群组选择器
    - 要求这些元素使用同样的样式规则，提出代码的公共部分，节约代码量
    - 使用的符号  ,
    - 语法
        - h1, #box, .demo{ }

8. 后代选择器
    - 使用符号  空格
    - 能够匹配子辈的元素，也能匹配孙辈的元素

9. 子代选择器
    - 使用符号 >
    - 只能匹配子辈的元素，不匹配孙辈

10. 伪类选择器
    - 通过鼠标触发，添加对应的样式
    - :link 访问前的样式
    - :visited 访问后的样式
    - :hover 鼠标经过的样式（经常使用）
    - :active 鼠标点击时的样式

11. 选择器的权值
    - ID > 类 > 标签
    - 如果使用不同的选择器修饰同一个元素的话，与代码执行的顺序没有关系，与选择器的权值有关
    - 涉及到的选择器权值
        - 通配符选择器      *        0
        - 标签选择器       p        1
        - 类选择器        .         10
        - id选择器        #         100
        - 行内样式表                 1000
        - !important               10000

12. css优先规则
    - 最近的祖先样式比其他祖先样式优先级高
    - “直接样式”比“祖先样式”优先级高
    - 优先级关系：内联（行内）样式 > ID选择器 > 类选择器 = 属性选择器 = 伪类选择器 > 标签选择器 = 伪元素选择器

# 六、注释
1. html注释
    <!--  ********  -->

2. css注释
    /*    ******    */

# ps简单操作
1. ctrl+"+" 放大画布
2. ctrl+"-" 缩小画布
3. 量尺寸工具：矩形选框工具（第二个图标）
4. 标尺：ctrl+R
5. 单位：标尺上右击修改单位，选择像素
6. 吸色：单击ps左下角前/背景色，画面中单击某个颜色，复制#色值即可
7. 拖动画布：按空格变小手，拖画布

# 作业
1. 整理笔记
2. 三遍练习法
3. 作业
    - 01 必做
    - 02 可选
4. 预习