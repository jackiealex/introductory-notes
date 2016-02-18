###yield 表达式
###——只有在生成器中才能使用yield表达式
####基本概念
```javascript
function *gen() {
	yield 1;
	yield 2;
	return 3;
}
```
+ 结束语句必须使用return
+ gen()并不运行任何结果，只是返回一个迭代器，iterator：iter = gen()
+ 并且 iter.next()返回一个结果：rs = iter.next(), 结构是这样的:｛value: 1, done: false|true｝
+ 当rs.done=true的时候，表示遇到了gen中的return语句

####使用co、generator、yield进行流程控制——顺序调用，异步执行
+ 先定义一个promise函数，用来模拟耗时任务
```javascript
var a = (sec = 1)=> {
	var promise = new Promise(function (resolve, reject) {
		setTimeout(function (argument) {
			var he = '1000 *' + sec + ' time:' + Date.now();
			console.log(he)
			resolve(he)
		}, 1000* sec)
	});
	return promise;
}
```
+ 再使用co 包裹generator 进行流程控制
```javascript
co(function *() {
	yield a(2);
	yield [a(3), a(10)]
	return a(4);
}).then((rs)=>{
	// console.log(rs)
})
```
