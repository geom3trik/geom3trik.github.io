---
layout: page
title: Understanding Layout
category: Layout
order: 1
---
---

The layout system in tuix is based on...

## Units

All layout properties use the same `Units` type. The `Units` type is defined as:

```rs
pub enum Units {
    Auto,
    Pixels(f32),
    Percentage(f32),
    Stretch(f32),
}
```

- `Auto` - Let the layout system determine the length based on either the parent properties or the child properties. We will cover this variant in more detail later.
- `Pixels` - Define the length based on a number of pixels.
- `Percentage` - Define the length as a percentage of the parent length.
- `Stretch` - Let the length stretch to fill a proportion of the remaining free space.

To see how the units work with the layout system, let's take a look at an example:

```rs
Button::new().build(state, window.entity(), |builder| 
    builder
        .set_width(Units::Pixels(100.0))
        .set_height(Units::Pixels(30.0))
        .set_background_color(Color::rgb(200,80,20))
);
}
```





