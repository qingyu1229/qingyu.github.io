---
layout: post
title: bootStrap插件 DataTables与X-Editable的综合
category: bootStrap
date: 2014-10-1
---

标签（空格分隔）： bootStrap Jquery

---

##前言

####我们在设计表格（table）的时候，往往需要给表格添加增、删、改、查的基本功能。利用bootstrap的各种相关插件可以轻松的在前台完成这些任务，而且又漂亮又简洁，后台只需通过ajax请求进行数据的交互就行。
    
##准备工作
### 1.引用的插件：
DataTables:  [下载点这里：）][1]  
X-Editable:  [下载点这里：）][2]

{% highlight java %}
需要引入的样式：
dataTables.bootstrap.css //DataTable的样式
bootstrap-editable.css   //X-Editable的样式
bootstrap.min.css        //bootStrap3的样式
需要引入的JS:
jquery-1.11.0.min.js        //bootStrap必须用它，你懂得
bootstrap.min.js            //bootStrap3的js
dataTables.bootstrap.js     //dataTables的js
bootstrap-editable.js       //x-editable的js
额外我引用了一个自己的主题：components.css layout.css
{% endhighlight %}

##开始
> 1.画一个表格：
{% highlight java %}
<table class="table table-striped table-hover table-bordered" id="table_1">
	<thead>
		<tr>
			<th>栏目1</th>
		    <th>栏目2</th>
			<th>栏目3</th>
			<th>栏目4</th>
		</tr>
	</thead>
	//tbody里将来会生成动态相应的单元格
	<tbody></tbody>
</table>
{% endhighlight %}
> 2.编写js主要的是如何将x-editable嵌套进dataTable中，为此我们要使用**fnDrawCallback**回调函数
这样我们就实现了改的功能
{% highlight java %}
$('table_1').dataTable({
    "lengthMenu": [
        [5, 15, 25, -1], //选择每页的条目数
        [5, 15, 25, "ALL"]
        ],
    "fnDrawCallback": function(){
        $.fn.editable.defaults.mode='popup';//设置默认模式
        //这里有个技巧，如何选中表中某一列
        $(this).find('td').each(function(i){
        if( i % num == 1)
            $(this).editable({
                type: 'text'//这里就可以设置各种属性了
                title: ''
                ....
            }).css("cursor", "pointer");
        });
            
        });
    }
});
{% endhighlight %}

 3.接下来就是删和增的操作了
 
 
  
 
[1]: http://www.datatables.net/download/index
[2]: http://vitalets.github.io/x-editable/
