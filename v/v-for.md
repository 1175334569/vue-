# v-for
  - ## v-for用于遍历数据
    - 格式：（item in items）
    		
			<li v-for="user in users"></li>
            //加上下标索引
			<li v-for"(user,index) in users"></li>
	- 遍历：
	
	        data:{
	            sums:['wo','ni',13,14],
	            others:{
	                name:'liang',
	                age:18,
	                score:100,
	            }
	        },
       - 遍历数组时
         `<li v-for"(value,index) in sums"></li>`
       - 遍历对象时
         `<li v-for"(value,key,index) in others"></li>`
  
  - ## 组件的key属性
    - 官方推荐我们在使用v-for时给对应的元素或者组件添加一个:key属性，来给每一个元素或者组件做一个唯一标识，可以更高效的更新虚拟dom。（不建议用Index，因为在中间插入元素时，index会发生变化，不能做到唯一性）。
 
  - ##数组的方法哪些是响应式的
    - push()  //在最后添加一个或多个元素
    - pop()//在最后移出一个元素
    - shift()//在最前移除一个元素
    - unshift()//在最前添加一个或多个元素
    - splice():splice作用：删除/添加/替换元素
    - sort()//排序
    - reverse()反转
  
  - <h5 style="color:red">注意：通过索引值修改的元素不是响应式的</h5>
  - 变成响应式方式：
    - 1:通过splice()函数进行修改
    - 2：通过Vue.set()进行修改
