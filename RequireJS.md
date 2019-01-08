- 详细文档参见**http://javascript.ruanyifeng.com/tool/requirejs.html**
- **requireJS**是一个工具库，主要用于客户端的模块管理，它可以让客户端的代码分成一个个模块，实现异步或动态加载，从而提高代码的性能和可维护性，它的模块管理遵循**AMD**（Asynchronous Module Definition）规范
- requireJS的基本思想是，通过define方法将代码定义为模块；通过require方法实现代码的模块加载。
1. define定义模块分两种情况，一种是不依赖其他模块的独立模块，另一种是依赖其他模块的非独立模块。
```
不依赖其他任何模块可以直接用define方法定义
define({
    method1: function() {},
    method2: function() {},
});
```
```
被定义的模块依赖其他模块
define(['module1', 'module2'], function(m1, m2) {
   return {
        method: function() {
            m1.methodA();
			m2.methodB();
        }
    };

});
define方法的第一个参数是一个数组，它的成员是当前模块所依赖的模块。
第二个参数是一个函数，它的参数与数组的成员一一对应，m1对应module1,这个函数必须返回一个对象，供其他模块调用
```