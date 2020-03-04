# "Oleg" starter pack

The files contained here are intended to provide a project agnostic starting point for your CSS to include in any web project. This version is pretty "bare bones" but will gradually evolve to include more useful features and utitlities.

This package is distributed through [npm](https://www.npmjs.com/).

## File structure

There are currently three directories, config, variables and utilities. They are intended to be used on any project but the key difference is how the code is used.

### Variables

Files in variables contains specific variables for breakpoints, fonts, etc.

### Config

Files in the config directory contain CSS which isn't targeted directly using a class but is compiled into the final CSS output (eg box-sizing or reset). It also contains usful mixins such as breakpoints.

### Utilities

Files in utilities contains useful, compact snippets of code which can be accessed directly using a class in your HTML

*Note* These files must be one of the last imported partials

## Install using npm

Before you can use npm, you need to [install Node](https://nodejs.org/en/download/).

Once you've done that, in the root of your project directory, run:

<pre>
    <code>
        npm install oleg-starter-pack
    </code>
</pre>

This will install the starter pack in the 'node_modules' directory located in the root of your project.

## Importing files located in node_modules

There are two methods of importing the files in this component. You can import them all in one go using the _include-all.scss file. Place the following code at the top of your main Sass file:

<pre>
    <code>
        @import "node_modules/oleg-starter-pack/all";
    </code>
</pre>

Note: You may need to customise the directory path in your imports, relative to where your main Sass file is located. For example:

<pre>
    <code>
        @import "../../node_modules/oleg-starter-pack/all";
    </code>
</pre>

Alternatively, you can include files individually to only use the files you need for a project. This option probably won't be needed in most cases but it's there if you need it.

<pre>
    <code>
        @import "node_modules/oleg-starter-pack/config/config.mixins";
        @import "node_modules/oleg-starter-pack/config/config.reset";
        @import "node_modules/oleg-starter-pack/config/config.breakpoints";
        @import "node_modules/oleg-starter-pack/config/config.box-sizing";
        @import "node_modules/oleg-starter-pack/utilities/utilities.clears";
        @import "node_modules/oleg-starter-pack/utilities/utilities.text-align";
    </code>
</pre>

Again, the directory path may need updating like the example above.

## Notes about specific files

The vast majority of the files in this component don't have any dependencies but occassionally some additional work in your project-specific Sass files will be needed to make use of some features.

### Gutters

The gutters file contains a simple Sass loop to give you a base level of options to create space between elements. In order to use this, you'll need to have a `$space` variable set in your project's Sass config file.

<pre>
    <code>
        $space: 15px;
    </code>
</pre>

Note: you'll need to ensure your config sits higher in your main Sass file than the gutter import. For example:

<pre>
    <code>
        @import "config/config";
        @import "bower_components/oleg-starter-pack/include-all";
    </code>
</pre>

Not doing so will throw an error because $space won't be defined if the bower component is called first.

Once this is set, you can use the class in your HTML. By default, you have 10 increments available, `u-gutter-bottom-[1-10]`, the Sass takes the number at the end and multiplies it by the value set to `$space`. So with the example `$space` variable set above, the rendered CSS will look like this:

<pre>
    <code>
        .u-gutter-bottom-1 { margin-bottom: 15px; }
        .u-gutter-bottom-2 { margin-bottom: 30px; }
        .u-gutter-bottom-3 { margin-bottom: 45px; }
        ...
        .u-gutter-bottom-10 { margin-bottom: 150px; }
    </code>
</pre>

If you need a bottom gutter larger than the default limit, seek help... or just hard-code it in your project. If there is a realistic use-case for increasing the default increments beyond 10, we need to review it before rolling it out.


--

Copyright 2017 Age Partnership Limited

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
