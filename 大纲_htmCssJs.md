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
### 文本样式
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