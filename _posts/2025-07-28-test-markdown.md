---
layout: post
title: Test
subtitle: Here is my test page
categories: markdown
tags: [test]
---
여기서 마크다운 형식으로 수정할 수 있습니다. 멋지게 사용해보세요<br>
You can write regular [markdown](https://markdowntutorial.com/) here and Jekyll will automatically convert it to a nice webpage.  I strongly encourage you to [take 5 minutes to learn how to write in markdown](http://markdowntutorial.com/) - it'll teach you how to transform regular text into bold/italics/headings/tables/etc.

**Here is some bold text**

## Here is a secondary heading

Here's a useless table:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |


How about a yummy crepe?

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg)

It can also be centered!

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg){: .center-block :}

Here's a code chunk:

~~~
var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.

### Emoji

This single quote code `inet:email:message:to` will not be parsed to emoji icon
:+1:.
