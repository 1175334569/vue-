## component组件的使用
  1. 创建组件构造器对象
  2. 注册组件
  3. 使用组件

			<script>
				//创建组件构造器对象
			    const cpnC = Vue.extend({
			        template: `<div>
			                      <div>我是标题</div>
			                      <h2>我是内容</h2>
			                  </div>`
			    });
				//注册组件
			    Vue.component('my-cpn', cpnC); //全局组件

			    const app = new Vue({
			        el: '#app',
			    })
			</script>
			//使用组件
			<div id="app">
			    <my-cpn></my-cpn> //要在new Vue挂载的实例里才能够使用
			</div>

#### 组件的语法糖注册方式
           Vue.component('my-cpn',{
			                 template: `<div>
			                      <div>我是标题</div>
			                      <h2>我是内容</h2>
			                  </div>`
				});
  - 省去了调用Vue.extend()的步骤。
  - 相当于把extend里的内容直接放到Vue.component里。其内部底层还是使用vue.extend()来实现。
#### 全局组件和局部组件
  - 全局组件：可以再页面任何有vue挂载实例的地方使用
  - 局部组件：只能在定义他的el中使用
  - 全局组件注册方式：
     				
        Vue.component('my-cpn', cpnC); //全局组件
  - 局部组件注册方式：
  
           const app = new Vue({
			        el: '#app',
					comoponents:{
						"my-cpn":cpnC,  //只能在app div里使用
						}
			    })
				//局部组件中语法糖写法
				components:{
					"my-cpn":{
			               template: `<div>
			                      <div>我是标题</div>
			                      <h2>我是内容</h2>
			                  </div>`
				             }
					}
         		
#### 父组件和子组件
  - 在一个组件里可以引入和使用另一个组件。

			    const cpnC1 = Vue.extend({    //子组件
			        template: `<div>
			                      <div>我是标题1</div>
			                      <h2>我是内容1</h2>
			                  </div>`
			    });
				const cpnC2 = Vue.extend({    //父组件
			        template: `<div>
			                      <div>我是标题2</div>
			                      <h2>我是内容2</h2>
								  <my-cpnC1></my-cpnC1>  //使用子组件cpnC1
			                  </div>`,
					components:{
						"my-cpnC1":cpnC1,  //引入子组件
					}
			    });
 