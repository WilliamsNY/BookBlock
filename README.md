# BookBlock: A Content Flip Plugin

A jQuery plugin that will create a booklet-like component that let's you navigate through its items by flipping the pages.

BookBlock is a plugin that can be used for creating booklet-like components that allow a “page flip” navigation. Any content can be used, such as images or text. The plugin transforms the structure only when needed (i.e. when flipping a page) and uses some overlays as shadow for the pages to create more realism.

The following structure will allow to add custom content in a wrapper with the class “bb-item”, which represents an open page (left and right side):

```
<div id="bb-bookblock" class="bb-bookblock">
    <div class="bb-item">
        <!-- custom content -->
    </div>
    <div class="bb-item">
        <!-- ... -->
    </div>
    <div class="bb-item">
        <!-- ... -->
    </div>
    <div class="bb-item">
        <!-- ... -->
    </div>
    <!-- ... -->
</div>
```

The plugin can be called like this:

```
$(function() {
    $( '#bb-bookblock' ).bookblock();
});
```

You also have to include the other scripts that are needed (see one of the demo files).

## Options

The following options are available:

```
// vertical or horizontal flip
orientation : 'vertical',

// ltr (left to right) or rtl (right to left)
direction : 'ltr',

// speed for the flip transition in ms.
speed : 1000,

// easing for the flip transition.
easing : 'ease-in-out',

// if set to true, both the flipping page and the sides will have an overlay to simulate shadows
shadows : true,

// opacity value for the "shadow" on both sides (when the flipping page is over it).
// value : 0.1 - 1
shadowSides : 0.2,

// opacity value for the "shadow" on the flipping page (while it is flipping).
// value : 0.1 - 1
shadowFlip : 0.1,

// if we should show the first item after reaching the end.
circular : false,

// if we want to specify a selector that triggers the next() function. example: '#bb-nav-next'.
nextEl : '',

// if we want to specify a selector that triggers the prev() function.
prevEl : '',

// If true it overwrites the circular option to true!
autoplay : false,

// time (ms) between page switch, if autoplay is true.
interval : 3000,

// callback after the flip transition.
// page is the current item's index.
// isLimit is true if the current page is the last one (or the first one).
onEndFlip : function( page, isLimit ) { return false; },

// callback before the flip transition.
// page is the current item's index.
onBeforeFlip: function( page ) { return false; }
```

The following public methods are available to use in combination with navigation elements:

* `$( ‘#bb-bookblock’ ).bookblock( ‘next’ )`
* `$( ‘#bb-bookblock’ ).bookblock( ‘prev’ )`
* `$( ‘#bb-bookblock’ ).bookblock( ‘jump’, position )`
* `$( ‘#bb-bookblock’ ).bookblock( ‘first’ )`
* `$( ‘#bb-bookblock’ ).bookblock( ‘last’ )`

## Demos

* Demo 1: Default configuration with navigation examples
* Demo 2: Horizontal flipping
* Demo 3: RTL Support (right-to-left support)
* Demo 4: Fullscreen example
* Demo 5: Multiple instances with dots navigation

