# Animated Appear CSS
A simple CSS library that adds show and hide animation to tiles with several options and multiple animations.

```html
<link rel="stylesheet" href="dist/animated-appear.min.css" type="text/css">
<link rel="stylesheet" href="dist/animations/all.min.css" type="text/css">
<div class="animate-appear all-children">
  <div style="--animation-item-index:0"></div>
  <div style="--animation-item-index:1"></div>
  <div style="--animation-item-index:2"></div>
  ...
</div>
```
## Classes
|Class|Description|
|------|----------|
|`animate-appear`|Add this class to the tiles' container.|
|`all-children`|This adds the animation to all children of the container. (Single level only.)|
|`show-all`|Plays the appear animation on all animated elements in the container.|
|`hide-all`|Plays the disappear animation on all animated elements in the container.|
|`show-me`|Plays the appear animation the the element with this class.|
|`hide-me`|Plays the disappear animation the the element with this class.|
|`animate-item`|Add this class to each element that will be animated. (To be used instead of `all-children`)|
## Options
|Option|Default Value| Description|
|------|-------------|------------|
|`--initial-delay`|0ms|Delay before animation starts.|
|`--timing-step`|20ms|Delay between each tile's animation.|
|`--animation-duration`|300ms|Duration of the animation of each tile.|
|`--animation-amplification`|1|Amount to amplify some animations. eg. A value of 2 will double the distance a tile will more. (This dose not effect rotations.)|
|`--appear-animation`|default-appear|Animation to play when tiles are made visible|
|`--disappear-animation`|default-disappear|Animation to play when tiles are made invisible|
|`--animation-item-index`|0|This defines what order the tiles should appear. (timing-step is multiplied with the index and added to the tile's animation delay, this option should be added to each tile.)|
|`perspective`|unset|A default CSS property which gives 3D rotations perspective. (Recomended for flip animations.)|
## Appear Animations
- default-appear
- slide-up-appear
- flip-center-horizontal-appear
- flip-top-vertical-appear
## Disappear Animations
- default-disappear
- slide-up-disappear
- flip-center-horizontal-disappear
- flip-top-vertical-disappear
## Timing Methods
### Pure CSS
`animated-appear-timings.min.css` Can be used to give upto 100 tiles indexes, however they must all share the same parent DOM element. The `all-children` class must be used on the parent.
```html
<link rel="stylesheet" href="dist/animated-appear-timings.min.css" type="text/css">
<div class="animate-appear all-children">
  <div></div>
  <div></div>
  <div></div>
  ...
</div>
```
### Adding indexes to the style attribute
`--animation-item-index` Can be added to each tile's style attribute, this could be done in javascript, during server side render of the page, or hard coded into the HTML.
```html
<div class="animate-appear all-children">
  <div style="--animation-item-index:0"></div>
  <div style="--animation-item-index:1"></div>
  <div style="--animation-item-index:2"></div>
  ...
</div>
```
This allows for the tiles to be in different hierarchical states.
```html
<div class="animate-appear">
  <span>
    <div class="animate-item" style="--animation-item-index:0"></div>
    <div class="animate-item" style="--animation-item-index:1"></div>
  </span>
  <div class="animate-item" style="--animation-item-index:2"></div>
  ...
</div>
```
