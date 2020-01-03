## vue-router的使用
  - ### vue-router的基本安装和配置 
	- 安装vue-router
	    > npm install vue-router --save
	- 第一步：导入路由对象，并且调用Vue.use(VueRouter)
	
			//配置路由相关信息
			import VueRouter from "vue-router";
			import Vue from 'vue'
			//通过Vue.use(插件)来安装插件
			Vue.use(VueRouter)
			const router=new VueRouter({
                //在routes里配置路由组件映射关系
			    routes:[],
                //配置路由模式
                mode: 'history'
			})
			export default router
	- 第二步：创建路由实例，并且传入路由映射配置
    - 第三步：在Vue实例中挂载创建的路由实例
    
			import Vue from 'vue'
			import App from './App.vue'
			import Router from './router/index'
			Vue.config.productionTip = false
			new Vue({
			  render: h => h(App),
              //挂载路由
			  router:Router
			}).$mount('#app')

  - ### vue-router的使用步骤
     - 第一步：创建路由组件
     - 第二步：配置路由映射：组件和路径映射关系
     - 第三步：通过<router-link>和<router-view>来使用路由
     
			<template>
			  <div id="app">
			    <router-link to="/home">首页</router-link>
			    <router-link to="/about">关于</router-link>      //决定映射到哪个组件
			    <router-view></router-view>                     //决定在哪个位置显示组件
			  </div>
			</template>

  - ###<router-link>的几个属性
     1. to属性：通过to属性指定目标地址，默认渲染成`<a>`标签，可以配置<tag>属性生成别的标签。
     2. tag属性：可以定义标签的类型
     3. replace属性：调用router.replace()方法而不是router.push()方法，跳转后不会留下记录，也就不能回退。
     4. append属性：在当前路径前添加基路径，例如从/a导航到相对路径/b，如果没有配置append,则路径为/b，如果配了则路径为/a/b.
     5. active-class属性：设置活跃链接的css类名。默认值为`router-link-active`。也可以通过路由的构造选项`linkActiveClass`来全局配置
         
			  {
			       path: '/user/:id',
			       component: User,
			       linkActiveClass: 'userClass'
			  }