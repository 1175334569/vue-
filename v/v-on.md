#v-on

- ## 简介
  - 在前端开发中，我们需要经常监听用户的某种行为，比如点击、拖拽等事件
  - 在vue中用v-on来绑定事件监听器
  - 缩写：@
- ## v-on的使用
  - 情况一：如果该方法不需要传递参数，则方法后面的小括号可以省略。
 在事件定义时，方法本身是需要一个参数的，如果省略了小括号。默认传一个浏览器生成的event事件对象作为参数传入到方法中。
		
			<button @click='btnClick'></button>
            //new Vue
    		methods:{
				btnClick(test){
				//这时test传入的就是event对象
				//如果调用时小括号没有省略，则test为undified
					}
				}