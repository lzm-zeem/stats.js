Stats.js
========

#### Javascript Performance Monitor ####

[![Flattr this](http://api.flattr.com/button/button-compact-static-100x17.png)](http://flattr.com/thing/1993/stats-js)

This class provides a simple info box that will help you monitor your code performance.

* **FPS** Frames rendered in the last second. The higher the number the better.
* **MS** Milliseconds needed to render a frame. The lower the number the better.
* **MEM** Mbytes of memory allocated. Make sure it doesn't keep incrementing. (Webkit-based browsers only)

### Screenshots ###

![stats_js_fps.png](http://mrdoob.github.com/stats.js/assets/stats_js_fps.png) ![stats_js_ms.png](http://mrdoob.github.com/stats.js/assets/stats_js_ms.png)  ![stats_js_mem.png](http://mrdoob.github.com/stats.js/assets/stats_js_mem.png)

### Usage ###

	var stats = new Stats();

	// Align top-left
	stats.domElement.style.position = 'absolute';
	stats.domElement.style.left = '0px';
	stats.domElement.style.top = '0px';

	parentElement.appendChild( stats.domElement );

	setInterval( function () {

		stats.update();

	}, 1000 / 60 );

### Enable MEM ###

* **Chrome**
  * Linux: `/opt/google/chrome/google-chrome --enable-memory-info`
  * Windows: `"C:\Program Files\Google\Chrome\Application\chrome.exe" --enable-memory-info`
  * MacOS: `/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --enable-memory-info`

* **Safari** 
  * MacOS: Open `~/Library/Preferences/com.apple.Safari.plist` file for editing, and add & set enabled a boolean preference *WebKitMemoryInfoEnabled* ([pic](http://mrdoob.github.com/stats.js/assets/safari_enablemem.png))

### Bookmarklet ###

The widget can also be used as a bookmarklet to monitor any website. Thanks to [@matthewlein](http://twitter.com/matthewlein) for the tip!

Drag and drop this link to your bookmarks toolbar: [Stats.js](javascript:(function(\){var script=document.createElement('script'\);script.type='text/javascript';script.src='http://github.com/mrdoob/stats.js/raw/master/build/Stats.js';document.body.appendChild(script\);script=document.createElement('script'\);script.innerHTML='var interval=setInterval(function(\){if(typeof Stats==\'function\'\){clearInterval(interval\);var stats=new Stats(\);stats.domElement.style.position=\'fixed\';stats.domElement.style.left=\'0px\';stats.domElement.style.top=\'0px\';document.body.appendChild(stats.domElement\);setInterval(function(\){stats.update(\);},1000/60\);}},100\);';document.body.appendChild(script\);}\)(\);)

[Hello](javascript:function my_bookmarklet(\){alert('Hello World'\);}my_bookmarklet(\);)

### Change Log ###

2010 09 21 - **r5** (3.800 kb)

* Different color per mode.
* Added MEM mode. (Webkit-based browsers only)
* Force text left aligned.


2010 06 11 - **r4** (2.235 kb)

* Added MS mode.


2010 05 12 - **r3** (1.241 kb)

* Switched to module pattern code style.
* Removed `position = 'absolute'`.


2010 03 01 - **r2** (2.177 kb)

* Simplified.


2010 02 21 - **r1**

* Accurate FPS calculation. (thx Spite!)

 
2009 08 09 - **r0**

* Base code.
