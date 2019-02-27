###  关于下拉框、复选框、单选按钮、多选按钮的选中状态的方法
1. 下拉框

``

    <select name="select" id="select">
		<option value="1" >1</option>
		<option value="2" selected="selected">2</option>
		<option value="3">3</option>
		<option value="4">4</option>
	</select>
``

    <select name="select1" id="select1" multiple="multipe">
		<option value="1" selected="selected">1</option>
		<option value="2" selected="selected">2</option>
		<option value="3">3</option>
		<option value="4">4</option>
	</select>


如果默认让它选中哪个就给哪个`<option value="2" selected="selected">2</option>` `<option></option>`标签添加selected属性

在jquery中的$.val()方法也可以做到这种选中效果，单选`$('#select').val(2)` 多选`$('#select1').val(['1','2'])`
或者`$('#select option:eq(1)').attr('selected',true)`也可以达到同样选中效果；
单选按钮和多选按钮同上，将selected变为checked，就行了
#### 注意： 在jquery.val()方法中  ` <option value="选中1号">选中2号</option> <option value="选中2号">选中1号</option>` $().val('选中1号')或者$().val('选中2号')都是选中的第二个，这个方法是从最后一个选项往前读取。