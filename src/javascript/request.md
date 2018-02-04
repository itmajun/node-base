# 网路请求
---


# Fetch
fetch用于获取网络请求, fetch 最终会返回一个promise对象.

```
// 通过fetch.返回promise, 通过then处理该对象.
fetch("/data.json").then(function(res) {
  // res instanceof Response == true.
  if (res.ok) {
    res.json().then(function(data) {
      console.log(data.entries);
    });
  } else {
    console.log("Looks like the response wasn't perfect, got status", res.status);
  }
}, function(e) {
  console.log("Fetch failed!", e);
});

//async-await语法

const response = await fetch(url, requestConfig);
const responseJson = await response.json();

```