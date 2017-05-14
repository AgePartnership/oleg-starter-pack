# "Oleg" starter pack

The files contained here are intended to provide a project agnostic starting point for your CSS to include in any web project. This version is pretty "bare bones" but will gradually evolve to include more useful features and utitlities.

## File structure

There are currently two directories, base and utilities. They are both intended to be used on any project but the key difference is how the code is used.

### Base

Files in the base directory contain CSS which isn't targeted directly using a class but is compiled into the final CSS output (eg box-sizing or reset). It also contains usful mixins such as breakpoints.

### Utitilities

Files in utilities contains useful, compact snippets of code which can be accessed directly using a class in your HTML

## Install using bower

First step is to install Bower: https://bower.io/#install-bower

Once you've done that, in the root of your project directory, run:

<pre>
    <code>
        bower install oleg-starter-pack --save
    </code>
</pre>

This will create the bower_components directory with the start pack so now you just need to include the files at the top of your primary Sass file:

<pre>
    <code>
        @import "bower_components/oleg-starter-pack/base/mixins";
        @import "bower_components/oleg-starter-pack/base/reset";
        @import "bower_components/oleg-starter-pack/base/breakpoints";
        @import "bower_components/oleg-starter-pack/base/box-sizing";
        @import "bower_components/oleg-starter-pack/utilities/clears";
        @import "bower_components/oleg-starter-pack/utilities/text-align";
    </code>
</pre>

Note: You may need to customise the directory path in your imports, relative to where your main Sass file is located. For example:

<pre>
    <code>
        @import "../../bower_components/oleg-starter-pack/base/mixins";
    </code>
</pre>

--

Copyright 2017 Age Partnership Limited

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.