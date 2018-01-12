
# 移动端调试工具框

----------


#### 1kb(gzip)代码搞定开发调试发布，错误监控上报，用户问题定位。


- 支持错误监控和上报
- 支持 vConsole错误展示
- 支持开发阶段使用 vConsole
- 支持生产环境机关拉取 vConsole
- 支持预埋机关唤起
- 支持url带参数唤起
- url带参数唤起有两个目的，第一是方便网站开发过程中显示vConsole面板，第二是发给投诉反馈网站错误的用户显示vConsole面板用于定位错误。


## 使用指南


	AlloyLever.config({
	    cdn:'//hd.huya.com/m_debug/vconsole.min.js',  //vconsole的CDN地址
	    reportUrl: "//a.xxx.com",  //错误上报地址
	    reportPrefix: 'qun',    //错误上报msg前缀，一般用于标识业务类型
	    reportKey: 'msg',        //错误上报msg前缀的key，用户上报系统接收存储msg
	    otherReport: {              //需要上报的其他信息
	        uin: 491862102
	    },
	    entry:"#entry"          //请点击这个DOM元素6次召唤vConsole。//你可以通过AlloyLever.entry('#entry2')设置多个机关入口召唤神龙
	})
AlloyLever会监听window.onerror并把错误信息保存下来，并且上报到reportUrl，你也可以召唤到vConsole并显示出来错误和相关日志。



### url唤起vConsole

	//加载并显示log面板
	http://localhost:63342/index.html?vconsole=show
	//加载但不显示log面板
	http://localhost:63342/index.html?vconsole=hide
	//不加载vConsole脚本
	http://localhost:63342/index.html


这些url的作用很好理解:

- 开发阶段用于调试
- 发给投诉的用户打开带有vconsole=show的url


### 也可以通过手势滑动出现，左下角-》顶部中间-》右下角



## 两种使用方式：

### 第一种   模块化引用

	require('m_debug')
	 AlloyLever.vConsole(true)  // 强制出来

### 第二种   直接copy引用

在你的页面任何地方引用下面脚本就可以，但是该js必须引用在其他脚本之前。
	
	<script src="//hd.huya.com/m_debug/m_debug-min.js"></script>

务必记住，该js必须引用在其他脚本之前！！


### 使用


	//测试console
    console.log('这是log信息')
    console.info('这是info信息')
    console.error('这是error信息')
    console.debug('这是debug信息')
    console.warn('这是warn信息')

