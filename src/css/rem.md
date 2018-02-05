# Rem
---

响应式框架的实现有多种方式, 目前rem使用的比较多. rem是一个单位名称.简称 em

根据窗体大小可以设置一个根font-size. 设置之后则 1rem = font-size. 如果不设置则走浏览器默认值. css中的字体,宽高就可以根据这个标准进行动态的变化进行适配.


这里有段代码: 初始化设计在iphone5. 320 ,提供默认 20px的font-size. 则在iphone5上面 1em= 20px. 如果375的iphone7上面则font-size=23.4375px. 对应的1em也会动态的放大.实现自适应的目的.

```
(function(doc, win) {
    var docEl = doc.documentElement,
        resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
        recalc = function() {
            var clientWidth = docEl.clientWidth;
            if (!clientWidth) return;
            docEl.style.fontSize = 20 * (clientWidth / 320) + 'px';
        };
    if (!doc.addEventListener) return;
    win.addEventListener(resizeEvt, recalc, false);
    doc.addEventListener('DOMContentLoaded', recalc, false);
})(document, window);

```

css专业人士一般通过css进行各种适配比如

```
html{font-size:10px}
@media screen and (min-width:321px) and (max-width:375px){html{font-size:11px}}
@media screen and (min-width:376px) and (max-width:414px){html{font-size:12px}}
```

