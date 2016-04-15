Grid
===

> Sweet responsive grids

## Why?
+ Only outputs only the CSS you use
+ Uses a combination of flex and calc to ensure accuracy
+ Keeps output small by extending classes, even within media queries
+ Uses Taffy's Break, a breakpoint system created for syncing grids and breakpoints
+ Includes a `$grid-fixed` variable to enable a responsive product grid style layout

## Getting Started
+ Install with Bower
+ Import the components

```
$ bower install --save taffy-grid
```

```scss
@import '../../bower_components/taffy-break/scss/main';
@import '../../bower_components/taffy-grid/scss/main';
```

## Grids
+ Initiate flex
+ Contain items

#### Markup

```html
<div class='grid'>
  <!-- items -->
</div>
```

## Items
+ Flex items
+ Not dependent on class names
+ Automatically extended, even within media queries
+ Wraps to a new line after the item limit has been reached

#### Markup

```html
<div class='grid'>
  <div class='item'></div>
  <div class='item'></div>
  <!-- break -->
  <div class='item'></div>
  <div class='item'></div>
</div>
```

#### Using items
+ The `item` mixin creates an item
+ Column amount is controlled by the `$break-amount` variable

This example item allows 2 items per line before wrapping to the next line.

```scss
.item {
  @include item(2);
  // ...
}
```

#### Using shorthand
+ Generates multiple breaks from a single line

The first arguments says: this item allows 2 items per line before wrapping to the next line.

The second argument says: after the browser width exceeds the width of the 6th break, this item allows 4 times per line before wrapping to the next line.

The third argument says: after the browser width exceeds the width of the 8th break, this item allows 6 times per line before wrapping to the next line.

```scss
.item {
  @include item(2 '6:4' '8:6');
  // ...
}
```

#### Using the fixed grid
+ Replaces the `flex` property in items with `width`

Before importing Taffy's Grid into your stylesheet set the `$grid-fixed` variable to `true`.

```scss
$grid-fixed: true;

@import '../bower_components/taffy-grid/scss/main';
```
