[![Haxelib Version](https://img.shields.io/github/release/pixijs/pixi-haxe.svg)](http://lib.haxe.org/p/pixijs) [![Build Status](https://travis-ci.org/notboring/pixi-haxe.svg?branch=dev)](https://travis-ci.org/notboring/pixi-haxe)
=========

### This fork

I am now one of maintainers for the official pixi repository. Find all future changes here: 

[Official pixi-haxe repository](https://github.com/pixijs/pixi-haxe)

~~This is not the official version! PIXI maintainers stopped accepting pull requests for the official haxe externs after [Adi Reddy sadly passed away](https://github.com/pixijs/pixi-haxe/issues/151). For that reason I created a fork that includes all pull requests from the official repository along with fixes from other forks. I also added a few pixi 4.8 changes myself.

~~Feel free to submit pull requests or issues if you see errors or want to improve this project. I'll try to keep these externs updated and also implement the 5.0 changes when they come out. 

~~If you want to help with managing this reposity please contact me using an issue. It would be a good idea to have at least one more person that can handle pull requests in case I am not available as much as I would like to.

=========
![haxe pixi logo](logo.png)

Externs of Pixi.js v4.x for Haxe - A fast and lightweight 2D javascript rendering library that works across all devices.

### Installation

```
haxelib git pixijs https://github.com/notboring/pixi-haxe.git dev
```

### Issues

Found any bug? Please create a new [issue](https://github.com/notboring/pixi-haxe/issues/new).

### Demos

* [Basics](http://adireddy.github.io/demos/pixi-haxe/basics.html)
* [Graphics](http://adireddy.github.io/demos/pixi-haxe/graphics.html)
* [Animated Sprite](http://adireddy.github.io/demos/pixi-haxe/animatedsprite.html)
* [Spritesheet](http://adireddy.github.io/demos/pixi-haxe/spritesheet.html)
* [Spine](http://adireddy.github.io/demos/pixi-haxe/spine.html)
* [Rope](http://adireddy.github.io/demos/pixi-haxe/rope.html)
* [Dragging](http://adireddy.github.io/demos/pixi-haxe/dragging.html)
* [Texture Swap](http://adireddy.github.io/demos/pixi-haxe/textureswap.html)
* [Tiling](http://adireddy.github.io/demos/pixi-haxe/tiling.html)
* [Bitmap Font](http://adireddy.github.io/demos/pixi-haxe/bitmapfont.html)
* [Alpha Mask](http://adireddy.github.io/demos/pixi-haxe/alphamask.html)
* [Bunnymark](http://adireddy.github.io/demos/pixi-haxe/bunnymark.html)
* [Retina](http://adireddy.github.io/demos/pixi-haxe/retina.html)
* [Events](http://adireddy.github.io/demos/pixi-haxe/events.html)
* [Loader](http://adireddy.github.io/demos/pixi-haxe/loader.html)
* [Video](http://adireddy.github.io/demos/pixi-haxe/video.html)
* [Nape](http://adireddy.github.io/demos/pixi-haxe/nape.html)
* [Dragon Bones](http://adireddy.github.io/demos/pixi-haxe/dragonbones.html)

**Filters (WebGL only)**

* [ColorMatrix](http://adireddy.github.io/demos/pixi-haxe/colormatrix.html)
* [Blur](http://adireddy.github.io/demos/pixi-haxe/blur.html)

**Filters (pixi-extra-filters)**
* [Glow](http://adireddy.github.io/demos/pixi-haxe/glow.html)

**[COHERE](http://adireddy.github.io/cohere/)** - Sample MVC application using Haxe and Pixi.js

Look at the `samples` folder for the source code of above examples.

### Usage

```haxe

import pixi.plugins.app.Application;
import pixi.core.graphics.Graphics;
import pixi.core.textures.Texture;
import pixi.core.sprites.Sprite;
import js.Browser;

class Main extends Application {

	var _bunny:Sprite;
	var _graphic:Graphics;

	public function new() {
		super();

		position = Application.POSITION_FIXED;
		width = Browser.window.innerWidth;
		height = Browser.window.innerHeight;
		backgroundColor = 0x006666;
		transparent = true;
		antialias = false;
		onUpdate = _animate;
		super.start();

		_bunny = new Sprite(Texture.fromImage("assets/basics/bunny.png"));
		_bunny.anchor.set(0.5);
		_bunny.position.set(400, 300);

		_graphic = new Graphics();
		_graphic.beginFill(0xFF0000, 0.4);
		_graphic.drawRect(200, 150, 400, 300);
		_graphic.endFill();

		stage.addChild(_graphic);
		stage.addChild(_bunny);
	}

	function _animate(e:Float) {
		_bunny.rotation += 0.1;
	}

	static function main() {
		new Main();
	}
}
```

### Licensing Information

<a rel="license" href="http://opensource.org/licenses/MIT">
<img alt="MIT license" height="40" src="http://upload.wikimedia.org/wikipedia/commons/c/c3/License_icon-mit.svg" /></a>

This content is released under the [MIT](http://opensource.org/licenses/MIT) License.

[Pixi.js](https://github.com/GoodBoyDigital/pixi.js) is licensed under the [MIT](http://opensource.org/licenses/MIT) License.

### Contributor Code of Conduct

[Code of Conduct](https://github.com/CoralineAda/contributor_covenant) is adapted from [Contributor Covenant, version 1.4](http://contributor-covenant.org/version/1/4)
