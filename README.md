lintel-contrib-grid
===================

> Grid for lintel.

[![npm](https://img.shields.io/npm/v/lintel-contrib-grid.svg)](https://www.npmjs.com/package/lintel-contrib-grid)
[![Bower](https://img.shields.io/bower/v/lintel-contrib-grid.svg)](https://github.com/lintelio/lintel-contrib-grid)


## Getting Started
This module requires Lintel.

If you haven't used [Lintel](http://lintel.io/) before, be sure to check out the [Getting Started](http://lintel.io/getting-started) guide, as it explains how to install and use this module. Once you're familiar with that process, you may install this module with this command:

```shell
bower install lintel-contrib-grid --save
```

Once the module has been installed, you will have to load it in your main SASS file:

```scss
@import "bower_components/lintel-contrib-grid/sass/grid.scss"
```

You can use [wiredep](https://github.com/taptapship/wiredep) or [grunt-wiredep](https://github.com/stephenplusplus/grunt-wiredep) to automatically inject files in your build process.


## Variables
Check the vars file in the `sass` folder to see the full list of variables you can customize.

#### $grid-columns
Default value: `12`  

Changes the number of columns for the default grid. Note: you can create additional grids using mixins (see below).

#### $grid-gutter
Default value: `30px`  

Change the gutter for the default grid.

#### $grid-breakpoint-min-map
Default value: `map-merge(("xs": 0), $screen-min-map)`  

A SASS map of the min-width of each breakpoint.

#### $grid-container-base-max-width
Default value: `$screen-lg-max`  

Default container max-width.


## Mixins
Check the mixins file in the `sass` folder to see how you can extend this module.

#### make-columns($columns, $gutter, $name, $suffix)
Default $columns: `$grid-columns`  
Default $gutter:  `$grid-gutter`  
Default $name:    `col`  
Default $suffix:  `null`  

Creates a new set of columns for each breakpoint.

- $columns: number of columns
- $gutter: width between columns
- $name: column class name prefix
- $suffix: whether to add `-of-*` where `*` is the total number of columns to each class

```scss
/* SASS */
@include make-columns(
  $columns: 10,
  $gutter: 20px,
  $name: "colten",
  $suffix: true
);
```

```css
/* CSS */
.colten-xs-1-of-10 { ... }
.colten-xs-2-of-10 { ... }
...
```


## Examples

#### Base
```html
<div class="container">
  <div class="row">
    <div class="col-md-4">...</div>
    <div class="col-md-4">...</div>
    <div class="col-md-4">...</div>
  </div>
</div>
```

#### Smaller Container
Use `.container-*` where `*` is the name of each breakpoint.

```html
<div class="container container-sm">...</div>
```

#### Offset
```html
<div class="container">
  <div class="row">
    <div class="col-md-4">...</div>
    <div class="col-md-8">...</div>
  </div>
  <div class="row">
    <div class="col-md-8 col-md-offset-4">...</div>
  </div>
</div>
```

#### Pull / Push
```html
<div class="container">
  <div class="row">
    <div class="col-xs-8 col-xs-push-4"><z>right</z></div>
    <div class="col-xs-4 col-xs-pull-8"><z>left</z></div>
  </div>
</div>
```


## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).


## License
Copyright (c) 2015 Marius Craciunoiu. Licensed under the MIT license.
