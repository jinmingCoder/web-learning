# html 表单
## 表单的概述
html表单是由一个或多个小部件组成，是用户和web 交互和传递数据的主要形式之一。

## 表单标签
form 标签
属性:
action 
method
## 小部件组
fieldset 标签：创建具有相同目的或语义的小部件组。
一般搭配legend 标签，对小部件组进行描述和说明。

## input标签
类型
text 输入框
password 密码框
hidden 隐藏内容，用于不对用户展示，服务器需要的字段。比如订单创建时间
checkbox 复选框
radio 单选按钮
button 按钮
reset 重置按钮
submit 提交按钮
image 图片按钮

file 文件类型：可以用来创建文件选择器

email 邮件类型
search 搜索类型
tel 电话号码类型
url 网址类型

number 数值类型

range 滑块类型

datetime-local 日期类型
month 月份类型
time 12/24小时类型
week 周数以及年份
date  日期类型，可配置步长
color 颜色类型

属性
id 唯一标识
name 传递json数据的key值。
value 默认的填充数值。
readonly 用户不能修改输入值。
disabled 输入值不会与表单数据的其余部分一起发送。
placeholder 文本输入框的默认文本。
size 框的物理尺寸。
minlength 可以输入的最小字符数。
maxlength 可以输入的最大字符数。
checked 单选和复选框默认选中的对象。

文件 类型
accept 上传文件的类型。
multiple 是否支持多文件上传。

数值/滑块/日期 类型
max 
min
step

## button标签
类型
submit 提交
reset 重置
button 通用按钮，没有实际意义需要配合js。
图片按钮（button标签包裹图片标签可以实现）
上面的按钮类型与之对应的，都会有一个input的展现形式。

## 多行文本标签
textarea 
属性
cols 指定文本控件的可见宽度（列）。默认是20
rows 指定控件的可见行数。默认是2
wrap （soft 默认值，在到达元素最大宽度的时候，换行显示，但是表单提交的时候不会包含换行符；hard 在文本到达元素最大宽度的时候，会主动插入换行符，提交的时候也会带上，但是需要指定cols属性）。
placeholder 文本的默认提示，特别需要注意。标签之间不能有空隙/空白
## 下拉列表
select 
子项组
optgroup （组的标题，可以用label属性）
子项
option

属性
multiple 列表是否支持多选，如果支持可以
按住键盘Cmd/Ctrl并单击桌面上的多个值。
size  列表最多显示几个子项。可用于确定列表最小高度。

## 弹出式菜单
datalist
子项
option

datalist标签需要配合input标签进行使用，
需要datalist的id属性和input的list属性进行绑定关联。

## datalist 和 select的区别
datalist可以自己输入，也可以选择。 select 只能选择。
但是select 支持多选，datalist 不支持多选。

## 多个标签
如果在一个小部件上可以放置多个标签，而在有多个标签的情况下，您应该将一个小部件和它的标签嵌套在一个<label>元素中。


## 表单元素包裹
通常我们用div 或 p 元素来包裹标签和小部件。
fieldset 来包裹同组的小部件。
section 来划分表单的不同部分。

## 其他标签
output 标签： 输出数值类型
progress 标签：进度条
属性：
max
value
step

meter 标签：指示器
三种颜色的仪表器
（三个部分： min - low， low - high， high - max)
min
low
high
max
optimum 定义meter元素的最佳值。
optimum 值在范围的较低部分。 那认为较低为最优，中等认为是平均，较高认为是最差。
optimum 值在范围的中间部分。 那认为较低为平均，中等认为是优选，较高为平均。
optimum 值在范围的较高部分。 那认为较低为最差，中等认为平均，较高为优选。


