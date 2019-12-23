## v-model
  - ### v-model基本使用
    - v-model用于数据的双向绑定
    - v-model只用于以下控件：
			      
			1.<input>
      		2.<textarea>
	        3.<select>
			4.components组件
  - ### v-model其实是一个语法糖，它实际完成了两个操作
    - 1.通过v-bind绑定一个value值。
    - 2.通过v-on监听当前input事件。
    		
				<input v-model="message">
				<input :value="message" @input="message=$event.target.value">
    			data:{
					message: '测试',
					}

  - ### v-model修饰符
     - #### lazy修饰符
        - 默认情况下，v-model是在input事件中同步输入框的数据的。lazy修饰符可以让数据输入时不发生同步，只有按回车或者失去焦点时才会同步。`v-model.lazy`
     - #### number修饰符
       - v-model传值默认为String类型。即时使用的是`<input type="number">`，如果想传的值为number类型，可以使用`v-model.number`绑定
     - #### trim修饰符
       - 除去两边的空格`v-model.trim`