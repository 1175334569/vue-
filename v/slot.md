## slot插槽
  - #### 组件的插槽让我们封装的组件更具有扩展性
    - 比如说一个导航栏在多个地方重复使用，但是导航栏里的内容不尽相同，这时我们就可以在不同之处插入一个插槽。具体内容由调用者自己定义

			<body>
				<!--     父模版-->
				   <div id="app">
				       <cpn><h4>我是导航栏1</h4></cpn>            //由父组件定义特定的属性
				       <cpn><h4>我是导航栏2</h4></cpn>
				       <cpn><h4>我是导航栏3</h4></cpn>
				   </div>
				<!--     子模版-->
				   <template id="capp">
				       <div>
				           <h2>我是标题</h2>
				          // <slot></slot>                         //子组件里用solt插槽预留，用于实现不同的地方
                             <slot><h4>我是导航栏</h4></slot>       //插槽内可以设置默认属性，当父组件调用时不定义则会显示默认属性
				           <h3>我是内容</h3>
				       </div>
				   </template>
			</body>
				<script>
				    //父组件
				    new Vue({
				        el:"#app",
				        methods:{
				        },
				        components:{
				            cpn:{
				                template:"#capp",
				            }
				        }
				    });
				</script>

  - #### 具名插槽
    - 当我们的组件需要实现多处不同的插槽时，这时就要给每个插槽起名让它们一一对应。
    
     			<body>
				<!--     父模版-->
				   <div id="app">
				       <cpn><h4>我是导航栏1</h4></cpn>            //由父组件定义特定的属性
				       <cpn><h4>我是导航栏2</h4></cpn>
				       <cpn><h4>我是导航栏3</h4></cpn>
                       <cpn><h6 slot="slot2">我才是真正的页脚</h6></cpn>        //定义slot的值对应插槽的name属性（不能直接写在组件里）
                                              //特别地，原本定义的标签和样式都会被替换
				   </div>
				<!--     子模版-->
				   <template id="capp">
				       <div>
				           <h2>我是标题</h2>
                           <slot><h4>我是导航栏</h4></slot>       //插槽内可以设置默认属性，当父组件调用时不定义则会显示默认属性
				           <h3>我是内容</h3>
                           <slot name="slot2"><h4 style="color:red">我是页脚</h4></slot>     //给插槽定义一个name属性
				       </div>
				   </template>
			</body>
				<script>
				    //父组件
				    new Vue({
				        el:"#app",
				        methods:{
				        },
				        components:{
				            cpn:{
				                template:"#capp",
				            }
				        }
				    });
				</script>