1. install nvm
   nvm 是nodejs 包管理工具，可以很方便的切换不同的版本的node，体验不同的特性
2. node version暂且切换到5.5吧
```shell
   nvm use 5.5
```
3. 安装 preset s2015
+ 猛戳 https://babeljs.io/docs/setup/#babel_cli 
```shell 
   npm install babel-preset-es2015
```
4. 在project／ 根目录下创建 .babelrc 文件，内容如下:
```javascript
{
	 "presets": ["es2015"]
}
```
