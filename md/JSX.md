# JSX #


----------

JSX，一种JavaScript的语法扩展。React使用JSX来替代常规的JavaScript，JSX会通过翻译器转换为纯JS再由浏览器执行。JSX是一个看起来很像XML的JavaScript语法扩展。React不需要一定使用JSX，但它有以下优点：

- JSX执行更快，因为它在编译为JavaScript代码后进行了优化；
- 它是类型安全的，在编译过程中就能发现错误；
- 使用JSX编写模板更加简单快速；

**JSX语法**

- 基本模板；

		const element = <h1>Hello, world!</h1>; // JSX不能加引号，加引号类型为字符串
		
		// 如果JSX为多行，使用括号将其包裹起来成为一个整体
		const element = ( 
			<h1 className = "h1">
				Hello, world!
			</h1>
		);

		// 纯JS写法，Babel转译器会把上面的代码JSX转换成一个名为React.createElement() 的方法调用，两者相同
		// React.createElement方法能生成元素
		const element = React.createElement(
			'h1',
			{
				className: 'h1' // 添加HTML属性
			},
			'Hello World!'
		);

- JSX当中可以使用JavaScript表达式，但表达式要包含在大括号里；

		const flag = true;
		const element = <h1>{ flag ? 'Hello' : 'Hi' }, world!</h1>; 

		// 上面代码解析为：
		const element = <h1>Hello, world!</h1>;

- 在编译之后呢，JSX会被转化为普通的JavaScript对象，所以可以像JS对象一样使用；

		// 可以作为返回值
		function a(val) {
		    return <h1>Hello, {val}!</h1>;
		}

		// 也可以在if、for语句中使用
		funcrion b(val) {
			if (val) {
				return <h1>Hello, world!</h1>;
			}
			return <h1>Hi, world!</h1>;
 		}

- JSX中的HTML属性；
		
		const cls = 'h1';
		const element = <h1 className={ cls }>Hello, world!</h1>; // JSX中的HTML属性使用驼峰写法，因为JSX是JavaScript的拓展，所以采用JS的写法。属性如果使用表达式就不要添加引号，否则会解析为字符串

		const element = <h1 className='h1'>Hello, world!</h1>; // 加引号的就是字符串属性

- 

		





