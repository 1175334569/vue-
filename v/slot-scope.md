## slot-scope作用域插槽
  - #### 在slot中，插槽由子组件定义，而显示的样式和内容都由父组件来决定。而作用域插槽内容由子组件来决定，父组件只决定显示的样式

  - ####  父组件替换插槽的标签，但是内容由子组件来提供
 
			<body>
			<!--     父模版-->
			   <div id="app">
			       <cpn>
			           <template slot="slot1" slot-scope="scope">     //slot-scope获取的是slot对象，对象名称可以任意写
			               <ul>
			                   <li v-for="item in scope.user">{{item}}</li>   //通过scope.user获取到user数据
			               </ul>
			           </template>
			       </cpn>
			       <cpn>
			           <template slot="slot1" slot-scope="user">
			               <span v-for="item in user.user">{{item}} + </span>   //通过user.user获取到user数据
			           </template>
			       </cpn>
			   </div>
			<!--     子模版-->
			   <template id="capp">
			       <div>
			           <h2>我是标题</h2>
			           <slot name="slot1" :user="user"></slot>   //将子组件user数据绑定到slot，绑定到哪个属性自己定义
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
			                data(){
			                    return{
			                        user:['liang','yong','xiang','shi','shui'],  //子组件定义user数据
			                    }
			                }
			            }
			        },
			
			    });
			</script>
    - 