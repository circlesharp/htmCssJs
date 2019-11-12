# 第一章_前端零基础入门

'''  
**标题分级说明**  
    一级标题 -> 章节  
    二级标题 -> 步骤  
    三级标题 -> 小节  
    四级标题 -> 知识点  
'''

## 步骤一_页面结构层HTML
    **代码** form_base.html
    **代码** form_input.html
    **代码** form_select.html
    **代码** index.html
    **代码** index2.html
    **代码** index3.html


## 步骤二_页面化妆师CSS

### 01-CSS选择的艺术
#### 为什么学习CSS
    1. CSS简化HTML相关标签，页面体积小，下载快
    2. 解决内容与表现分离的问题
    3. 更高地维护页面，提高工作效率
#### 要学习的内容
    1. CSS基础语法
    2. CSS使用方法
    3. CSS选择器
    4. CSS继承和层叠
    5. CSS优先级
    6. CSS命名规范
#### CSS基础语法
    **代码** css_base.html
    CSS规则：
        选择器 + 声明（好像就是一个字典）
#### 如何引用CSS样式
    **代码** css_use.html
    **代码** css.css
    1. 行内样式（内联样式）
    2. 内部样式表（嵌入样式）
    3. 外部样式表
        -> 最常用，一般来说优先级也最低（行内 > 内部 > 外部）
        -> 但是，优先级遵守就近原则（我觉得和Python顺序执行相通）
    4. 导入式（也属于内部，因为在style标签里面）
#### CSS选择器
    **代码** css_selector.html
    1. 标签选择器 标签名
    2. 类选择器 .
    3. ID选择器 #
    4. 全局选择器 *
    5. 群组选择器 ,
    6. 后代选择器 space
    7. 伪类选择器 :
        :link       未访问的链接
        :visited    已访问的链接
        :hover      鼠标悬停状态(鼠标放在上面)
        :active     激活的链接（鼠标按住不松开）
        **有顺序的**
#### CSS 继承、层叠、优先级、权值
    1. 继承
        解决低级浏览器的继承问题，可以使用群组选择器方式
        有些标签本来就有特定的样式，优先级比较高
    2. 层叠
        1. 可以定义多个样式
        2. 不冲突时，多个样式可层叠为一个
        3. 冲突时，按不同样式规则优先级来应用样式
    3. 优先级
        1. 权值相同
            就近原则
        2. 权值不同
            行内 > 内部 > 外部
            id > class > 标签 > *
    4. 权值
        1. 具体权值
            !important      最高……
            行内样式        1000
            ID选择器        100
            类选择器、伪类  10
            标签选择器      1
            通配符          0
        2. 计算规则 -> 加权求和
            如：#main div.warning h2{}
                id:1 class:1 标签:2
                -> 100 + 10 + 2 = 112
#### CSS命名规则
    1. 可用"_"、"-", 但不能作为开头；
    2. 命名形式
        单字    special
        连字符  main-title
        下划线  main_title
        驼峰    mainTitle
    3. id不要滥用；适当使用class


### 02-CSS文本样式
#### 学习内容
    1. 文字
        颜色、字体大小、字体、加粗……
    2. 文本
        行高、对齐方式、文本装饰……
#### 字体样式
    font-family:
        1. 字体名[,字体名][,字体集]
        2. 设置多个属性可应对字体缺失的尴尬局面（使用常字体）
        3. 正文字体集建议选 sans-serif
    font-size:
        1. 绝对单位（CSS2缩放系数为 1.2）：
            in, cm, mm, pt, pc
            xx-small, x-small, small, medium, large, x-larg, xx-large
        2. 相对单位
            px  # 受显示器分辨率影响，一般不适用（特别是手机端）
            em / %  # 根据夫元素字体大小而定（继承）
    color：
        3种写法
    缩写：
        {font: font-style font-variant font-weitht font-size/line-height font-family}
        注意顺序，空格隔开
#### 文本样式
    text-align（文本对齐）
        仅对块级元素有效
        解决方法，在外部增加一个<div>，就能继承样式
    line-height（行高，浏览器默认行高为 120% / 1.2em )
        可以使用绝对和相对单位，建议使用相对的 em, %
        注意：行高继承的是计算值（也就是绝对值），不会继承相对值。所以要重新设置。
    vertical-align（垂直对齐）
        掌握“基线”的定义，也可以使用绝对值和相对值。
        对行内元素、单元格起作用。
        注意：如果对块级元素进行垂直居中，可以将其转化为单元格（display:tabel display:table-cell）
    word-spacing
        -> 设置元素内 单词 之间的间距
        判断标准以 space 为基准
    letter-spacing
        -> 设置元素内 字母 之间的间距
        判断标准为每一个字（不论是应为字母，还是汉字块）
    text-transform（设置大小写）
        capitalize, uppercase, lowercase, none
    text-docoration（设置元素内文本的装饰）
        underline, overline, line-through, blink, none
### 03-盒子模型
    1. 宽度属性 width
        （IE6不支持：max-width | min-width）
        设置内容的宽度
    2. height 也是这样的
    3. width 与 height 的适用范围
        1. 块级元素
            <p> <div> <h1~h6> <ul> <li> <ol> <dl> <dt> <dd>
        2. 替换元素-> 浏览器根据其标签的元素与属性来判断显示的具体内容
            <img> <input> <textarea>
    4. border 边框属性
        1. border-width border-color border-sytle
            border-color: 颜色、transparent（透明）
            border-sytle：要先定义，否则边框的颜色也不会显示
        2. 方向
            border-[left | right | top | bottom]-width|color|sytle
            如：border-left-color
        3. 缩写
            border: 宽度 样式 颜色;
    5. padding 内边距
        1. 内容到边框的距离
        2. 盒子在网页中占的空间，不单单与width和height属性相关，还与padding有关。
        3. 缩写
            padding: up
            padding: ub rl
            padding: u rl b
            padding: u r b l
        4. 注意，padding 不能设为负值；margin 可以设置为负值。
    6. margin 外边距
        1. 和padding缩写一样
        2. margin 为 auto，实现水平方向居中显示效果  // 常用
        3. 相邻 margin 取最大
    7. display属性
        1. inline
        2. block
        3. inline-block
        4. none
### 05-float浮动
    1. css定位机制
        1. 普通流（标准流）
            默认状态，从左往右，从上到下
            注意：行内元素不能设置宽高
        2. 浮动
        3. 绝对定位
    2. 浮动（Float）的基础知识
        1. 会使元素向左、向右移动，只能左右，不能上下。
        2. 浮动元素碰到 包含框 或者 另一个浮动框 ，浮动停止。
        3. 浮动元素之后的元素将围绕它，之前的不受影响。
        4. 最开始的时候，是用来做文字环绕图片的效果
        5. 虽然浮动之后脱离了文档流，但是仍在文本流当中。
    3. Float的基本语法
        1. float: left
        2. float: right
        3. float: none
    4. 清除浮动语法
        clear: none|left|right|both;
    5. 浮动的问题：
        1. “高度塌陷” -> 浮动溢出
            元素使用浮动后会脱离普通流，出现“高度塌陷”。
        2. 区分文本流、标准流
            如果只给box_01设置浮动，02的盒子不见了，但是文本还留着。
            如果只给box_01、02设置浮动，03盒子不见了，但文本留着01的下面，高度塌陷。
            如果给3个盒子都设置浮动，容器就没有高度了，浮动溢出。再添加一个大一点的box_04,升上去了，但是文字会尾随，颜色在后面。
    5. 清除浮动常用方法
        1. 在浮动元素后使用一个空元素IE
            如： <div class="class"></div>
        2. 给浮动元素的容器（父元素）添加
            overflow: hidden;
            zoom: 1;  // 兼容垃圾IE
        3. 使用CSS3的 :after伪元素（给夫元素添加类名，弄一个假的空元素；主流）
            .clearfix:after{content:"."; display:block; height:0; visibility:hidden; clear:both;}
            .clearfix{zoom: 1;}
        4. 给容器定义高度，不让它崩塌（只适合高度固定的布局）
        5. 歪门邪道：容器也一起浮动（不推荐）

### 06-CSS定位(position)
#### 1. static
        1. static/静态定位/常规定位/自然定位（从左往右，从上到下）
        2. 使元素定位于常规/自然流中
        3. 会忽略 top, bottom, left, right, z-index 声明
        4. 当具有固定的 width，margin的左右都设置为auto，则水平居中
#### 2. relative
        0. 使元素成为 containing-block | 官话就是：可定位的祖先元素
        1. 可以使用 top/right/bottom/left/z-index 进行相对定位
        2. 相对定位的元素不会离开常规流  ——  心念家乡
        3. 任何元素都可以设置为relative，它的绝对定位的后代都可以相对于它进行绝对定位  ——  超级好用
        4. 可以使浮动元素发生偏移，并控制它们的堆叠顺序
            对于浮动的，将position设为relative,就可以通过 top, bottom, right, left 去让它偏移
            并且通过z-index调整堆叠顺序（例子，小人骑小马）
#### 3. absolute  --  实际工作用的最多，同时也比较难
        1. 脱离常规流
            使元素脱离常规流(把家里房卖了，出去北漂；relative是北漂但是家里还有房)
        2. 设置尺寸的时候，百分比相应的是最近定位祖先元素
            如果都没有，就认 <body> 为爹
        3. lrtb如果设置为0，会对齐到最近定位祖先元素的各边————衍生出一个居中妙计
        4. z-index可以控制堆叠顺序999999
        5. 任何元素都可以设置为relative，它的绝对定位的后代都可以相对于它进行绝对定位  ——  超级好用
            通过调整 top, bottom, left, right
        6. 如果要居中，就固定宽高之后（父元素要求相对定位），将margin设置为 auto
        7. 如果要覆盖夫元素，就不设置（因为会继承）
#### 4. fixed
        1. 和 absolute 本是同根生
        2. 区别就在于相对于谁定位
            absolute    ->  容器
            fixed       ->  视口