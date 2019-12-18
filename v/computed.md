#computed
  - ##computed计算属性
     > 在模版中，我们可以用{{}}插入数据来显示一些data中的数据，但在一些时候我们需要对数据经行一系列的计算和加工才将它显示出来，这时候直接在{{}}里写代码就会显得非常臃肿。而且在特定的场合下并不适用。比如：将一个数组累加后输出。这时候，我们就可以用计算属性来完成计算和加工的一系列操作。    
         
         <div id="app">
         <h2>{{getAll}}</h2>
         </div>
         new Vue({
         el: '#app',
         data:{
            people:[
                {name: 'aa', score: 18},
                {name: 'ss', score: 1},
                {name: 'dd', score: 15},
                {name: 'ff', score: 17},
            ]
         },
         computed :{
            getAll:function () {
               let sum=0;
                for(let i=0;i<this.people.length;i++){
                    sum+=this.people[i].score;
                }
                return sum;
            }
         }
        })

  - ##computed的get和set
  	- 计算属性的完整写法
  		
    		computed :{
              getAll: {
                set:function () {},
                get:function () {
                    let sum=0;
                    for(let i=0;i<this.people.length;i++){
                        sum+=this.people[i].score;
                    }
                    return sum;
                }
              }
        	}
	
	- 一般情况下，计算属性是不设置set方法的，所以一般写法省略掉set方法，只留get方法。
	
  - ##computed和methods的区别
     - 缓存：methods方法没有缓存，每次调用时都会执行一次。而computed有缓存机制。当多次调用时只执行一次，只有computed里数据变化时才会重新执行。