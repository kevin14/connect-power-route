# connect-power-route
Nodejs connect的路由模块，将express的路由操作习惯抽取出来支持connect

# 使用

```
npm install connect-power-route --save
```

```js
var cpr = require('connect-power-route');
	connect = require('connect'),
	app = connect();

app.use(cpr(function (router) {
	router.get('/', function (req, res, next) {
		res.end('index');
	});

	router.get('/home', function (req, res, next) {
		res.end('home');
	});

	router.get('/home/:id', function (req, res, next) {
		res.end('home ' + req.params.id);
	});

	router.post('/home/:id(\\d{0,4})', function (req, res, next) {
		res.end('POST to home');
	});
}));
```
