# js捕获、冒泡事件
  - ##在多层结构标签中，捕获是从父节点走向子节点。而冒泡是从子节点上升到父节点

		<body>
		<div id="grandfather" class="grandfather">grandfather
		    <div id="father" class="father">father
		        <div id="son" class="son">son</div>
		    </div>
		</div>
		</body>
		<script>
		    var grandfather = document.getElementById("grandfather");
		    var father = document.getElementById("father");
		    var son = document.getElementById("son");
		
		    grandfather.addEventListener('click',function () {
		        alert('grandfather');
		    });
		    father.addEventListener('click',function () {
		        alert("father");
		    });
		    son.addEventListener('click',function () {
		        alert("son");
		    })
		</script>
![图片](images/js事件冒泡.png)
    
    