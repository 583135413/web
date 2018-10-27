## 定义Vue组件
什么是组件： 组件的出现，就是为了拆分Vue实例的代码量的，能够让我们以不同的组件，来划分不同的ui功能模块（例如轮播图），将来我们需要什么样的功能，就可以去调用对应的组件即可；
组件化和模块化的不同：
 + 模块化： 是从代码逻辑的角度进行划分的；方便代码分层开发，保证每个功能模块的职能单一；
 + 组件化： 是从UI界面的角度进行划分的；前端的组件化，方便UI组件的重用；
 ### 全局组件定义的三种方式
1. 使用 Vue.extend 配合 Vue.component 方法：
  + Vue.extend命名时使用**驼峰命名法**  'myComp' 则使用时把**驼峰改成** '-' <my-comp></my-comp>
```
var login = Vue.extend({
      template: '<h1>登录</h1>'
    });
    Vue.component('login', login);
```
2. 直接使用 Vue.component 方法：
```
Vue.component('register', {
      template: '<h1>注册</h1>'
    });
```
3. 将模板字符串，定义到script标签种：
```
<script id="tmpl" type="x-template">
      <div><a href="#">登录</a> | <a href="#">注册</a></div>
    </script>
```
同时，需要使用 Vue.component 来定义组件：
```
Vue.component('account', {
      template: '#tmpl'
    });
```
4. 将模板字符串，定义到script标签种：
```
 <template id="tmpl">
    <div>
      <a href="#">登录</a> | <a href="#">注册</a>
    </div>
  </template>
```
同时，需要使用 Vue.component 来定义组件：
```
Vue.component('便签名', { //在vue控制区使用方法 
      template: '#tmpl'
    });
```
如何使用自定义组件
```
 <div id="app">1
    <login></login>
 </div>
```
> 注意： 组件中的DOM结构，有且只能有唯一的根元素（Root Element）来进行包裹！就是需要把所用的结构包裹在一个标签内 就是放在一个div里面 不要<div></div><div></div>
