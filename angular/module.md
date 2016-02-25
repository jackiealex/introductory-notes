###module定义

 module 是一个controller、service、factory、provider等的集合
 module 的定义可以声明依赖其它modules
```javascript
angular.module('helloModule', ['moduleA', 'moduleB']);
```

###module使用
 module的使用可能依赖其它module，因此一定要保证其它的module已经加载执行了，eg
```html
<head>
	<script src="moduleA.js"></script>
	<script src="moduleB.js"></script>
	<script src="helloModule.js"></script>
</head>
```
or
```javascript
require(['moduleA', 'moduleB'], function() {
	angular.module('helloModule', ['moduleAProvider', 'moduleBService']);
})
```
or
```javascript
define(['moduleA', 'moduleB'], function() {
	angular.module('helloModule', ['moduleAProvider', 'moduleBService']);
})
```


