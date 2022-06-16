# 弹性盒子
## Flex
弹性盒子是一种用于按行或按列布局元素的一维布局方法。元素可以膨胀填充额外的空间，收缩以适应更小的空间。

[参考地址:](https://www.zhangxinxu.com/wordpress/2018/10/display-flex-css3-css/)

### flex 弹性模型
给div这类块状元素元素设置display:flex或者给span这类内联元素设置display:inline-flex，flex布局即创建。
区别在于：inline-flex容器为inline特性，因此可以和图片文字一行显示；flex容器保持块状特性，宽度默认100%，不和内联元素一行显示。

flex 的父元素被称为flex容器（flex container）
flex容器中的柔性的盒子的元素被称为flex项 (flex item)
主轴（main axis）是沿着flex元素放置的方向延伸的轴（比如页面上的横向的行，纵向的列）。开始和结束被称为main start 和main end。
交叉轴（cross axis）是垂直于flex元素放置方向的轴。

### 作用容器
flex-direction：控制子项整体布局。
row，row-reverse，column，column-reverse
默认，显示行。方向为当前文档水平流方向，默认是从左到右。
注意此处说当前文档水平流方向。

flex-wrap：用于控制子项整体单行/还是换行显示。
如果换行，则下面一行是否反方向显示。
nowrap, wrap, wrap-reverse。
wrap-reverse 宽度不足换行显示，也就是原本换行在下面的子项现在跑到最上面一行。

flex-flow：属性是flex-direction 和 flex-wrap的缩写，表示flex
布局的flow流动特性。
当多属性同时使用的时候，使用空格分隔。

justify-content：属性决定了水平方向子项的对齐和分布方式。CSS text-align有个属性值为justify，可实现两端对齐。所以记住它也就记住了justify-content。
flex-start/end 与文档流方向相关。左对齐/右对齐。
center，居中对齐。
space-between 两端对齐。意思是多余的空白间距只在元素中间区域分配。
space-around around是环绕的意思，意思是每个flex子项两侧都环绕互不干扰的等宽的空白间距。最终效果是中间的间隔是二端的二倍。
space-evenly evenly均称，平等。在视觉上所有的空白完全相等分布。

align-items：items指的就是flex子项们，因此align-items指的就是flex子项们相对于flex容器在垂直方向上的对齐方式。
stretch
默认值。flex子项拉伸，子项的高度拉伸到容器高度。而flex子项设置了高度，则按照设置的高度值渲染，不是拉伸。
flex-start/end 与文档流方向相关。容器顶部/底部对齐。
center垂直居中对齐。
baseline 表现为所有flex子项都相对于flex容器的<strong>基线对齐。</strong>

align-content：可以看成和justify-content是相似且对立的属性，justify-content指明水平方向flex子项的对齐和分布方式，而align-content则是指明垂直方向每一行flex元素的对齐和分布方式
stretch
默认值。每一行flex子元素都等比例拉伸。例如，如果共两行flex子元素，则每一行拉伸高度是50%。
flex-start/end 与文档流方向相关。默认表现为顶部/底部堆放。
center整体垂直居中对齐。
space-between 上下两行两端对齐。剩下每一行元素等分剩余空间。
space-around
每一行元素上下都享有独立不重叠的空白空间。
space-evenly
每一行元素都完全上下等分。


### 作用子项
order：改变某一个flex子项的排序位置。默认都是0，如果想让某个子项
显示在最前面，可以设置比0小的整数，如-1。

flex-grow：属性中的grow是扩展的意思，扩展的就是flex子项所占据的<strong>宽度</strong>，扩展所侵占的空间就是除去元素外的剩余的空白间隙。
flex-grow 不支持负值，默认是0，表示不占用剩余的空白间隙扩展自己的宽度。如果flex-grow 大于0，则flex容器就会按照比例进行分配间隙。

flex-shrink 收缩，flex-shrink主要处理当flex容器空间不足时候，单个元素的收缩比例。flex-shrink不支持负值，默认值是1，也就是默认所有的flex子项都会收缩。如果设置为0，则表示不收缩，保持原始的fit-content宽度。

上面二个属性，如果同组子项中只有一个子项设置了此属性，则按照小于1，则扩展/收缩部分尺寸，大于1则完全扩展/收缩尺寸。而如果有多个子项设置了此属性，则计算算子项的总和，小于1，则收缩/扩展不完全，按照比例进行收缩/扩展。大于1，则收缩/扩展完全，每个子项按照比例进行收缩/扩展。

flex-basis：定义了在分配剩余空间之前元素的默认大小。相当于对浏览器提前告知：浏览器，我要占据这么大的空间，提前帮我预留好。
默认值是auto，就是自动。有设置width则占据空间就是width，没有设置就按内容宽度来。
如果同时设置width和flex-basis，就渲染表现来看，会忽略width。flex顾名思义就是弹性的意思，因此，实际上不建议对flex子项使用width属性，因为不够弹性。

flex
属性是flex-grow， flex-shrink 和flex-basis的缩写。
flex: none | auto | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]。
其中第2和第3个参数是可选的。默认为0  1  auto。

flex默认值等同于flex:0 1 auto；
flex:none等同于flex:0 0 auto；
flex:auto等同于flex:1 1 auto；

align-self：指控制单独某一个flex 子项的垂直对齐方式。

