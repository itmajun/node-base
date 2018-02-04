# javascript 循环语法

* for
```
for (var i=0; i<5; i++){}
```
* for...of
```
//循环出来的是对象值
for(var value of aArray){
    console.log(value);
}
```
* for...in
```
//ES6语法.循环出来是key
for(let index in aArray){
    console.log(`${aArray[index]}`);
}
```
* Object.keys
```
Object.keys(data).forEach(key => {
            dataStr += key + '=' + data[key] + '&';
        })
```
