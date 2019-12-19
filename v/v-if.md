# v-if、v-else-if、v-else
   - ## 条件判断，没什么好说的
     - v-if可以根据值在dom中渲染或者销毁元素和组件（v-show只是隐藏）
   - ## 组件复用问题
     - 当互斥条件有相同控件时：该控件复用，比如input里输入的文字切换到另一个条件时不会删掉。如果不想该控件被复用。可以加一个不同的key属性来标识该控件。
     
     		<span v-if=true>
			    <input id="username" key="username">
			</span>
			//互斥条件
			<span v-else>
			    <input id="email" key="email">
			</span>

