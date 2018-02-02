# Router
---

vue + vue-router 可以非常简单的创建单页应用。
简单的原理就是， 我们想知道 路由和组件 关联起来。 通过访问指定的路由/login 指定Login组件。

* 创建组件
* 定义路由， 其中指定了路由和组件的映射
* 创建Router对象
* 绑定Vue


# 路由

```
const routes = [
  { path: '/foo', component: Foo },

  // 动态路由
  { path: '/bar/:id', component: Bar }，

  //嵌套路由
  { path: '/bar/:id', component: Bar,
	children: [

		// 映射到 /bar/:id/test
		{ path: 'test', component: Test},
	]
  }
]


//路由操作

router.push('home')
router.push({ path: 'home' })
router.push({ name: 'user', params: { userId: 123 }})
//带查询参数，变成 /register?plan=private
router.push({ path: 'register', query: { plan: 'private' }})

//使用path时候，params会被忽视
// 命名， 自动name的做法更普遍
router.push({ name: 'user', params: { userId }}) // -> /user/123
router.push({ path: `/user/${userId}` }) // -> /user/123

// back 操作
router.go(1)
router.go(-1)

//命名视图是一种路由分组，指定view中的某一部分。不指定时候是default
const router = new VueRouter({
  routes: [
    {
      path: '/',
      components: {
        default: Foo,
        a: Bar,
        b: Baz
      }
    }
  ]
})

// 重定向
const router = new VueRouter({
  routes: [
    { path: '/a', redirect: '/b' }，
    // 通过name
    { path: '/a', redirect: { name: 'foo' }}，
    // 访问/a 不改变url，跟访问／b一样都指向A
    { path: '/a', component: A, alias: '/b' }
  ]
})

// props

{ path: '/user/:id', component: User, props: true },

``` 
# 总结
---
越看越复杂， 这东西不用会让人迷糊死