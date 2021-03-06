```
title: "Hello World Command Line"
```
Hello world is a [common example](http://en.wikipedia.org/wiki/Hello_world_program) of getting started with programming, here we will show you how to add Hello World with HaxeFlixel's FlxText. You can compile this test for any supported target platform.

Using the command line with HaxeFlixel is made easier with our custom built flixel-tools utility, also made with `Haxe`;

#### Install Flixel Tools

Installing the tools is as easy as installing flixel:

``` bash
haxelib install flixel-tools
```

#### Setup the Tools

Setup the tools so that it can download dependencies for the commands and set your preferences:

``` bash
haxelib run flixel-tools setup
```

#### Create a new HaxeFlixel Project Template

HaxeFlixel requires a basic structure of files for any project that you can automatically create with a simple command. To see the parameters of this command type;

``` bash
flixel tpl -n "Hello World"
```

The extended docs for the flixel-tools can be [found here](/documentation/flixel-tools).

You will now see a new Hello World folder with all the files for your project created automatically.

#### Add the Hello World FlxText

Adding the text as as simple as opening the MenuState.hx file in the newly created source folder.

The file will look like this:

``` haxe
package;

import openfl.Assets;
import org.flixel.*;

class MenuState extends FlxState
{
	/**
	 * Function that is called up when to state is created to set it up. 
	 */
	override public function create():Void
	{
		// Set a background color
		FlxG.bgColor = 0xff131c1b;
		// Show the mouse (in case it hasn't been disabled)
		#if !FLX_NO_MOUSE
		FlxG.mouse.show();
		#end

		super.create();
	}

	/**
	 * Function that is called when this state is destroyed - you might want to 
	 * consider setting all objects this state uses to null to help garbage collection.
	 */
	override public function destroy():Void
	{
		super.destroy();
	}

	/**
	 * Function that is called once every frame.
	 */
	override public function update():Void
	{
		super.update();
	}	
}
```

All you need to do is add the following in the create() method:

``` haxe
add(new FlxText(0, 0, 100, "Hello World!")); 
```

Your MenuState.hx should now look like this:

``` haxe
package;

import openfl.Assets;
import org.flixel.*;

class MenuState extends FlxState
{
	/**
	 * Function that is called up when to state is created to set it up. 
	 */
	override public function create():Void
	{
		// Set a background color
		FlxG.bgColor = 0xff131c1b;
		// Show the mouse (in case it hasn't been disabled)
		#if !FLX_NO_MOUSE
		FlxG.mouse.show();
		#end

		//Lets say Hello by using add with a new FlxText :)
		add(new FlxText(0,0,100,"Hello World!"));

		super.create();
	}

	/**
	 * Function that is called when this state is destroyed - you might want to 
	 * consider setting all objects this state uses to null to help garbage collection.
	 */
	override public function destroy():Void
	{
		super.destroy();
	}

	/**
	 * Function that is called once every frame.
	 */
	override public function update():Void
	{
		super.update();
	}	
}
```

Save MenuState.hx and return to your command line window. Now we can compile Hello World with openfl.

Without running the [OpenFL setup](/documentation/install-openfl) commands you can compile to Flash and Neko out of the box.

Test your project from the following commands:

``` bash
openfl test flash
```

``` bash
openfl test neko
```

If you struggled through any part of this tutorial ask a question on our [forum](/forum) :)

<img src="/images/hello-world.jpg" style="width:100%;" />