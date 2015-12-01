### 参考于 [互联网公司2014前端笔试面试题JavaScript篇](http://www.codeceo.com/article/2014-javascript-interview.html)

```javascript
// 1. 用js实现随机选取10–100之间的10个数字，存入一个数组，并排序
! function() {
	var arr = [];
	var getRandomNumber = function() {
		return parseInt(Math.random() * 90 + 10);
	};
	for (var i = 0; i < 10; i++) {
		arr.push(getRandomNumber());
	}
	var arr = arr.sort(function(a, b) {
		return a - b;
	});
	console.log(arr);
}()

/**
 * 2. 有这样一个URL：http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e，
 * 请写一段JS程序提取URL中的各个GET参数(参数名和参数个数不确定)，
 * 将其按key-value形式返回到一个json结构中，
 * 如{a:'1', b:'2', c:'', d:'xxx', e:undefined}。
 *
 * 从这道题目我看见自己的不足
 * 在match、replace方法上、正则表达式的不足
 */

! function() {
	var url = 'http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e';
	var json = {};
	var matches = url.match(/(\?|\&)(\w+)=(\w+)/);
	console.log(matches);
}()

/**
 * 3. setTimeout一些用法
 */
! function() {
	for (var i = 1; i <= 3; i++) {
		setTimeout(function() {
			console.log(i);
		}, 0);
	};

	for (var i = 1; i <= 3; i++) {
		setTimeout((function(a) { //改成立即执行函数
			console.log(a);
		})(i), 0);
	};
}()

/**
 * 4. 我们要给每个log方法添加一个(app)前缀，
 * 比如'hello world!'->'(app)hello world!'
 *
 * forEach 这个函数还不是很熟悉
 */
! function() {
	var log = function() {
		var prefix = '(app)';
		return function() {
			var args = [].slice.call(arguments);
			args.forEach(function(item, index, arr) {
				arr[index] = prefix + item;
			});
			console.log(args);
		}
	}();
	log('monkindey','zhangkaihao');
}()

```

### 欢迎补充
