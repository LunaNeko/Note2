= css基础笔记


= 标签选择器,通过标签名来 找到元素
		p{
			font-size: 40px;
		}
= id选择器 通过id 找到元素 前边需要加#
		#p1{
			color: red;
		}

= class选择器 ,通过class名 找到元素 ,前边需要加.
		.text{
			color: blue;
		}

		<link rel="stylesheet" href="">引用别的css文档

		<!-- css书写格式 -->
		p{
			color: red;
		}

= 交集 选择器
		同时具有 text 和 danger 这两个class名的元素
		.text.danger{
			color: red;
		}

= 并集选择器
		选中 h2 标签  和 p 标签
		h2,p{
			color: orange;
		}

= 后代选择器
		.box .inner-box{
			color: blue;
		}(两个class之间加空格)

 = 通配符(*)

		 选中所有标签 (并集选择器)
		字体颜色 继承了父类的字体颜色 字号
		a标签 不会继承父类的颜色

		行内样式(1000) > id选择器权重高(100) > class选择器(10) > 标签选择器(1) 继承属性,通配符权重为0
		权重一样怎么办?*/
		权重一样的话  ,后写的 会覆盖 前边写的 (就近原则)

= 块状标签(元素)
		自动换行
		可以设置宽高有效
		宽度不写的情况下,默认100%  -->
		div h1 h6  p ul li  ol li dl dt dd table form
	


= 行内元素
		不会自动换行 
   	 	设置宽高 无效
	
= 字体标签

		行内块元素
		不会自动换行
		设置宽高 有效
	

= 背景图片
		background-repeat: repeat-x
		background-repeat: repeat-y
		background-repeat: repeat
		第一个值  水平方向 left center right
		第二个值  垂直方向 top center  bottom
		background-position: right center
		垂直方向不写  默认为center
		background-position: center
		第一个值  距离左边的像素
		第二个值   距离上边的像素

		*简写*
		background: #000 url() no-repeat center;
= padding border margin
		
		padding 内边距(填充物)
		border 边框(快递盒子厚度)
		margin 外边距  快递(盒子) 和快递(盒子) 之间的 间距*/

		设置的宽高  作用在  content(内容区域)

= padding
		内部填充
           分别设置某个方向 的padding
			padding-top: 10px
			padding-left: 20px
			padding-right: 30px
			padding-bottom: 40px
			background-color: red
			padding 改变了 元素 在页面当中占据的空间大小 (改变了盒子的大小)
			上下左右 四个方向  都是20px
			padding: 20px
			第一个 上下  第二个 左右
			padding: 20px 10px
			 上   左右    下
			padding: 10px 20px 30px
			上  右  下   左 

= border
			外边框
			简写
			border: 15px solid orange;
			单独对某个方向上的border 设置
			border-bottom: 5px solid transparent;

= margin
			两个盒子之间的距离
			简写方法和padding一样
			当margin出现嵌套崩塌时,在父级盒子里输入overflow:hidden;

= 浮动      
			float:left;
			块级元素和行内元素都可以浮动，当一个行内元素浮动以后将会自动变为一个块级元素.
			当一个块级元素浮动以后，宽度会默认被内容撑开，所以当漂浮一个块级元素时我们都会为其指定一个宽度。
			脱离了文档流,下边的元素 会上移
			元素浮动以后即完全脱离文档流，这时不会再影响父元素的高度。也就是浮动元素不会撑开父元素。

= 清除浮动影响
     		overflow: hidden;
			clear:both;

= 伪类      
			hover
			a:hover(当鼠标放在a标签上时,会出现预设好的变量)

= 定位	
			position属性可以把一个元素放置到网页中的任何位置。
			可选值：
			– static (默认)
			– relative (相对定位)
			– absolute (绝对定位)
			– fixed (固定定位)
			**相对定位不会改变元素原来的特性

= 绝对定位
			绝对定位
			距离 body 左边 上边的距离
			position: absolute;
			left: 100px;
			top: 100px;
			position: relative;
			子绝父相（子类想要 相对于 父类  做 绝对定位，但是父类我没有定位属性，name我们给父类添加  一个  相对定位 position：releative）
			绝对定位 到底是  相对谁(参照物)  做定位

			元素相对于离他最近的祖先定位元素进行定位或者html元素。

=z-index
			有定位属性,才能设置z-index
			改变定位覆盖顺序优先级
			