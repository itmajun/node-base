# vue :class
---
vue 绑定 class 对象.

```
<div v-bind:class="{ active: isActive }"></div>
```
接受map形式的class, 其中 后面的数据如果为false 则前面不显示.


```
 let classList = [
                    `${prefixCls}`,
                    {
                        [`${prefixCls}-span-${this.span}`]: this.span,
                        [`${prefixCls}-order-${this.order}`]: this.order,
                        [`${prefixCls}-offset-${this.offset}`]: this.offset,
                        [`${prefixCls}-push-${this.push}`]: this.push,
                        [`${prefixCls}-pull-${this.pull}`]: this.pull,
                        [`${this.className}`]: !!this.className
                    }
                ];

```

比如上面语法: 接受数组参数.使用了对象语法.