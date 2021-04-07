---
title: Inline Styling
category: Styling
order: 2
---
---

Tuix provides inline styles which directly affect an element and cannot be overrriden by shared styles (which includes from CSS).

There are two ways to set an inline style property:

1. By calling `set_property_name(value)` on the `builder` argument of the closure when building a widget. For example, setting the width and height of widget during building:

    ```rs
    let my_button = Button::new().build(state, parent, |builder| {
            builder
                .set_width(Units::Pixels(200.0))
                .set_height(Units::Pixels(200.0))    
    });
    ```

2. By calling `set_property_name(state, value)` on the entity id of a widget. For example:
    ```rs
    let my_button = Button::new().build(state, parent, |builder| builder);

    my_button
        .set_width(state, Units::Pixels(200.0))
        .set_height(state, Units::Pixels(200.0));
    ```
    In this case `state` must be passed to the property setting functions.