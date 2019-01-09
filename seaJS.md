- 详细文档参见**https://www.cnblogs.com/goloving/p/7712310.html**
- seaJS也是用JavaScript编写的JS框架，主要功能是可以按不同的先后依赖关系对JavaScript等文件的进行加载工作，可简单的理解为JS文件的加载器。他非常适合在浏览器中使用，可以确保所依赖的JS文件加载完成之后再加载当前的JS文件，这在大量使用JS文件的项目中可确保各个JS文件的先后加载顺序，确保避免了以前因某些原因某个文件加载慢而导致其他加载快的文件需要依赖其某些功能而出现某函数或某变量找不到的问题**SeaJS(遵守CMD规范)**
  - seaJS.config({});//用来对seaJS进行配置
  - seaJS.use(['a','b'],function(a,b){});//用来在页面中加载一个或多个模块
  - define(function(require,exports,module){});//用来定义模块，一个模块一个文件
  - require(function(require){var a=require('xModule')});//require用来获取指定模块的接口
  - require.async;//用来在模块内部异步加载一个或多个模块，例如：
  ```
  define(function(require){
      require.async(['aModule','bModule'],function(a,b){
          a.func();
          b.func();
      }
  })
  ```
    - exports  //用来在模块内部对外提供接口，例如：
    ```
    define(function(require,exports){
        exports.varName01='varValue';
        exports.funName01=function(p1,p2){}
    })
    ```
    - module.exports   //与exports类似，用来在模块内部对外提供接口，例如：
    ```
    define(function(require,exports,module){
        module.exports={
            name:'a',
            doSomething:function(){};
        }
    })
    ```
