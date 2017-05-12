移动端调试工具框
=========



##两种使用方式：

### 第一种   模块化引用

	require('m_debug')

### 第二种   直接copy引用

在你的页面任何地方引用下面脚本就可以，但是该js必须引用在其他脚本之前。
	
	<script src="m_debug.js"></script>

务必记住，该js必须引用在其他脚本之前！！


### 使用


	//测试console
    console.log('这是log信息')
    console.info('这是info信息')
    console.error('这是error信息')
    console.debug('这是debug信息')
    console.warn('这是warn信息')

