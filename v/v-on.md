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

  - 情况二：方法传入时，我们要传入参数，同时还需要event对象。  
     - 使用`$event`获取。
     		
				<button @click='btnClick(123,$event)'></button>
				//new Vue
				methods:{
					btnClick(abc,event);   //可以获取到参数以及event事件对象
					}

- ## v-on的一些修饰符
  - `.stop` //阻止冒泡 ，js中的event.stopPropagation();
  - `.prevent` //阻止默认事件，js中的event.preventDefault();
  - `@keyup`监听键盘事件
  - `.native` //监听组件根元素的原生事件
  - `.once`//只触发一次回调