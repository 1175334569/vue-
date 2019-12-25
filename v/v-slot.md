## v-slot
  - #### 在vue 2.6.0后，使用v-slot指令代替slot和slot-scope指令
  
   	      	<body>
			<!--     父模版-->
			   <div id="app">
			       <cpn>
			           <template slot="slot1" slot-scope="scope">     //slot-scope获取的是slot对象，对象名称可以任意写
        *********************      //   <template v-slot:slot1="scope">   //使用v-slot获取
			               <ul>
			                   <li v-for="item in scope.user">{{item}}</li>   //通过scope.user获取到user数据
			               </ul>
			           </template>
			       </cpn>
			       <cpn>
			           <template slot="slot1" slot-scope="user">
        **********************     //   <template v-slot:slot1="user">   //使用v-slot获取
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