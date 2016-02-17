###yield 表达式
###——只有在生成器中才能使用yield表达式
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
