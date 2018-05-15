---
title: SVG
description: Performant styler for SVG elements
category: styler-types
---

# SVG styler

The SVG styler replaces the confusing SVG transformation model with the CSS model and provides a simple API for `path` drawing.

## Path drawing

Line drawing the process of using an SVG `path` element and its `stroke-dasharray` and `stoke-dashoffset` properties to emulate a pen drawing a line. [This blog post](https://css-tricks.com/svg-line-animation-works/) explains the effect in more detail.

Stylefire supports both`'stoke-dasharray'` and `stroke-dashorigin` properties, but also provides:

* `pathLength`
* `pathSpacing`
* `pathOffset`

These are all set as a **progress of the total path length, from `0` to `1`**, which is automatically measured by Stylefire.

So you can define an animation from `0` to `100`:

```javascript
import { tween } from "popmotion";
import styler from "stylefire";

const path = document.querySelector("path");
const pathStyler = styler(polygon);

tween({ to: 100 }).start(v => pathStyler.set("pathLength", v));
```

In this example you can change the real `path` shape and length without having to update the animation.

## Props

### Supported props

**All SVG attributes are supported**.

## Prop types

For convenience and safety, many props are mapped to [value types](/api/value-types) for safety and convenience.

* `fill`: `color`
* `stroke`: `color`
* `scale`: `scale`
* `scaleX`: `scale`
* `scaleY`: `scale`
* `opacity`: `alpha`
* `fillOpacity`: `alpha`
* `strokeOpacity`: `alpha`