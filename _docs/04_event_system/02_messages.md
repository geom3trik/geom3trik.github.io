---
layout: page
title: Messages
category: Event System
order: 2
---
---

# Message

A message is any rust `struct` or `enum` that implements `Debug`, `Clone` and `PartialEq`. Below is an example of a message enum used by the `Textbox` widget:

```rs
#[derive(Debug, Clone, PartialEq)]
pub enum TextboxEvent {
    SetValue(String),
    ValueChanged(String),
}
```

The `SetValue` variant is used to tell the textbox to change its value and originates from another widget. The `ValueChanged` variant is emitted by the textbox when the user changes the text inside the textbox.