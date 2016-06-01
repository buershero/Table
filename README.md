# Table

table colgroup  col

---
###标签组成元素

**caption**
其中：caption [带有标题的表格] 只用于table
参考：[https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption][1]

----------

**colgrounp**
HTML表格中列组元素(< colgroup >)，定义了一组列，可以利用它对表格列做控制。
样例：
####带有colgroup的表格
```html
<table>
   <caption>表头<caption>
   <colgrounp>
   <col>列的属性</col>
   <col>列的属性</col>
   </colgrounp>
   <thead>
      <tr>
         <th scope="col">列</th>
         <th scope="col">列</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>数据</td>
         <td>数据</td>
      </tr>
   </tbody>
   <tfoot></tfoot>
</table>
```
scope属性：
使用 scope 属性，可以将数据单元格与表头单元格联系起来。通过属性值 row，表头行包括的所有表格都将和表头单元格联系起来。指定 col，会将当前列的所有单元格和表头单元格绑定起来。
使用 rowgroup 和 colgroup 会将单元格的行组（由 <thead>、<tbody> 或 <tfoot> 标签定义）或列组中的所有单元格和表头单元格绑定起来（由 <col> 或 <colgroup> 标签定义）。

显示结果：
![此处输入图片的描述][2]


----------


colgrounp具有的属性 参考：[https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/colgroup][3]

 - algin (html4.0之后已废弃)
 - bgcolor (不建议使用)
 - char （html4.0之后已废弃 指定列中字符的对齐展示）
 - charoff (html4.0之后已废弃)
 - span (包含一个正整数表示连续的列的数量< colgroup >元素范围。如果不存在,它的默认值是1。)
 - valign (html4.0之后已废弃)
 - width (指定列的宽度)


**其它**
col 中依照不同场景可能会用到的属性：
 - the : width
 - the : nth-child
 - the : text-algin

对 span 的使用
```html
<table class="table">
	<colgroup>
	<col class="vzebra-even" span="2">
	<col class="vzebra-odd">
	<col class="vzebra-even">
	<col class="vzebra-odd">
	</colgroup>
	<thead>
		<tr>
			<th>test</th>
			<th>test</th>
			<th>test</th>
			<th>test</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>显示数据</td>
			<td>显示数据</td>
			<td>显示数据</td>
			<td>显示数据</td>
		</tr>
		<tr>
			<td>显示数据</td>
			<td>显示数据</td>
			<td>显示数据</td>
			<td>显示数据</td>
		</tr>
	</tbody>
	<tfoot>
	<td>总计：</td>
	<td>155,101,00</td>
	<td>155,101,00</td>
	<td>155,101,00</td>
	</tfoot>
</table>
```
显示结果：
![此处输入图片的描述][3]


**table中属性的特殊用法，或许它能帮助我们解决很多繁琐的问题**

```
tbody > tr:nth-of-type(odd) {
    background-color: yellow;
  }
```
使用伪类e:nth-of-type(odd)/(even)对表格奇偶行进行颜色变化，有了它从此实现table striped so easy!
*e:nth-of-type(2n+1),此处N表示为任意数字。*

```
table {
  td,
  th {
    &[class*="col-"] {
      position: static;
      float: none;
      display: table-cell;
    }
  }
}
```
css3中属性选择器：
E[att^="val"]	CSS3	选择具有att属性且属性值为以val开头的字符串的E元素。（开头）
E[att$="val"]	CSS3	选择具有att属性且属性值为以val结尾的字符串的E元素。（结尾）
E[att*="val"]	CSS3	选择具有att属性且属性值为包含val的字符串的E元素。  （包含有）


---------


  [1]: https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption
  [2]: http://p8.qhimg.com/t0199b223d0b0137b81.jpg
  [3]: http://p2.qhimg.com/t01ff8c8700bf39a4f4.jpg
