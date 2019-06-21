```HTML

<iframe id="iframe01" src="html02.html"></iframe>
<script>
window.onload = function(){
	// window.frames 属性和 window.length 属性
	console.log( window.frames );								// Window {postMessage: ƒ, blur: ƒ, focus: ƒ, close: ƒ, parent: Window, …}
	console.log( window.frames === window );					// true # window.frames 其实就是等于 window
	console.log( window.length );								// 1 # 如果页面中没有 iframe 也没有 frame，那么 window.length 就等于 0
	console.log( window.length === window.frames.length );		// true # 因为 window.frames 就等于 window，所以这两个比对的属性值就是同一个
	// window.frames 属性的元素都是 window
	console.log( window.frames[0] );							// Window html02.html # 这样获取的是 iframe01 的 window
	console.log( window.frames[0].location.href );				// http://192.168.1.199:8041/99-test/html02.html # iframe01 的地址
	// 在全局中自动生成的标签 id 值变量
	console.log( iframe01 );									// HTMLIframeElement / Window html02.html # Firefox & Chrome 是 HTMLIframeElement，IE 是 Window html02.html
	console.log( iframe01.contentWindow );						// Window html02.html / undefined # Firefox & Chrome 是 Window html02.html，IE 是 undefined，因为 window 上没有 contentWindow 属性
	// 原生 JS 操作 iframe 标签
	var iframe01Ele = document.getElementById('iframe01');		// 必须要用选择方法选择标签，不能拿全局中自动生成的对象
	console.log( iframe01Ele );									// HTMLIFrameElement
	console.log( iframe01Ele.contentWindow );					// Window html02.html 
	console.log( iframe01Ele.contentDocument  );				// Document html02.html
	// jQuery 操作 iframe 标签
	console.log( $('#iframe01').contents() );					// Object[Document html02.html]
	console.log( $('#iframe01').contents().find('head') );		// Object[head]
};
</script>

```
