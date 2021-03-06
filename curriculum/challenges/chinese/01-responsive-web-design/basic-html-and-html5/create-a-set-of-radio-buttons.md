---
id: bad87fee1348bd9aedf08834
title: 创建一组单选按钮
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cNWKvuR'
forumTopicId: 16822
---

# --description--

`radio buttons`（单选按钮）就好比单项选择题，正确答案只有一个。

单选按钮是`input`选择框的一种类型。

每一个单选按钮都应该嵌套在它自己的`label`（标签）元素中。

所有关联的单选按钮应该拥有相同的`name`属性。

下面是一个单选按钮的例子：

```html
<label> 
  <input type="radio" name="indoor-outdoor">Indoor 
</label>
```

最佳实践是在`label`元素上设置for属性，让其值与单选按钮的`id`属性值相等，这样就在`label`元素和它的子元素单选按钮之间创建了一种链接关系。例如：

```html
<label for="indoor"> 
  <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
</label>
```

# --instructions--

给表单添加两个单选按钮，一个叫`indoor`，另一个叫`outdoor`，单选按钮的 `name` 为 `indoor-outdoor`。

# --hints--

页面上应该有两个单选按钮元素。

```js
assert($('input[type="radio"]').length > 1);
```

设置单选按钮的`name`属性为`indoor-outdoor`。

```js
assert($('input[type="radio"]').filter("[name='indoor-outdoor']").length > 1);
```

每一个单选按钮都应该嵌套进它自己的`label`元素中。

```js
assert($('label > input[type="radio"]:only-child').length > 1);
```

每一个`label`元素都有结束标记。

```js
assert(
  code.match(/<\/label>/g) &&
    code.match(/<label/g) &&
    code.match(/<\/label>/g).length === code.match(/<label/g).length
);
```

其中一个`label`元素的文本为`indoor`。

```js
assert(
  $('label')
    .text()
    .match(/indoor/gi)
);
```

其中一个`label`元素的文本为`outdoor`。

```js
assert(
  $('label')
    .text()
    .match(/outdoor/gi)
);
```

所有的单选按钮都应该包含在`form`表单中。

```js
assert($('label').parent().get(0).tagName.match('FORM'));
```

# --solutions--

