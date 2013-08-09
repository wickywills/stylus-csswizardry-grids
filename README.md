# stylus-csswizardry-grids

This is a port of Harry Roberts' csswizardry-grids into **Stylus**.
It has all the functionality of the Sass version, with added features:

* `use_floats`: By default, this is set to `true`, resulting in behavior
  identical to the original library. However, setting it to `false` allows
  you to use `float: left` instead of `display: inline-block` for the grid's
  basic scaffolding. This alleviates some of the spacing issues inherent to
  `display: inline-block`; however, right-, center-, middle- and bottom-aligned
  grid layouts currently don't work with floated mode.
* **Customization**: the grid class selectors are generated using interpolation
  of a small number of variables. Tweaking class names, e.g. shortening `.grid`
  to `.gw` and `.grid__item` to `.g`, is now very easy to accomplish by editing
  those variables.

Also, a few missing features have been added back:

* `use_silent_classes`: presumably, you're going to use this grid with Stylus.
  This allows you to completely eschew grid classes from your markup, and use
  the grid via `@extend`. When `use_silent_classes` is `true`, only classes that
  are actually `@extend`ed in your stylesheets will be generated, saving you
  a few kilobytes.
* `use_markup_fix`: when `true`, leaves solving the spacing issues inherent to
  `display: inline-block` up to you - e.g. by setting `font-size: 0` on the
  grid container, or by eliminating all whitespace between grid items in your
  markup. When this variable is set to `false`, an empirically determined fix
  is applied. It gives small negative values to the properties `letter-spacing`
  and `word-spacing`, which fixes the spacing issue across browsers, but is not
  guaranteed to be bulletproof.

**Simple, fluid, nestable, flexible, Stylus-based, responsive grid system.**

* Fully responsive
* Infinitely nestable
* Endless possible combinations
* Simple to understand, human-friendly classes
* Option to keep classes out of your HTML
* Robust
* Simple
* No `.clear` or `.last` classes
* It just _works_

Please see [Responsive grid systems; a solution?](http://csswizardry.com/2013/02/responsive-grid-systems-a-solution/)
for a comprehensive overview of the principles of the grid system.

## Setup

Simply fill in/adjust the relevant variables.

* `$gutter` controls how much space there is between columns.
* `$lap-start` and `$desk-start` tell csswizardry-grids when to fire particular
  media queries to service those particular sizes. Note that csswizardry-grids
  works out the ends of any other breakpoints by using these numbers.

## Basic usage

If you are using traditional classes then an example, basic usage might look
like this:

    <div class="grid">
    
        <div class="grid__item  lap-one-half  desk-two-thirds">
            ...
        </div>
    
        <div class="grid__item  lap-one-half  desk-one-third">
            ...
        </div>
    
    </div>

There is a very simple demo which can be found at
[csswizardry.github.com/csswizardry-grids](http://csswizardry.github.com/csswizardry-grids).
