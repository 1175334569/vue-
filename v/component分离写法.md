## component模版的分离写法
   1. 使用script标签，类型`type="text/x-template"`
   
			<div id="app">
			    <my-cpn></my-cpn>
			</div>
			
			<script type="text/x-template" id="cpn">    //定义id属性
			   <div>
			       <h2>我是标题</h2>
			       <h3>我是内容</h3>
			   </div>
			</script>
			<script>
			    Vue.component("my-cpn",{
			        template: "#cpn",           //根据id调用模版
			    });
			    const app = new Vue({
			        el: '#app',
			    })
			</script>
   2. 使用template标签
   
			<div id="app">
			    <my-cpn></my-cpn>
			</div>
			
			<template id="cpn">               //定义id属性
			    <div>
			        <h2>我是标题</h2>
			        <h3>我是内容</h3>
			    </div>
			</template>
			<script>
			    Vue.component("my-cpn",{
			        template: "#cpn",           //根据id调用模版
			    });
			    const app = new Vue({
			        el: '#app',
			    })
			</script>