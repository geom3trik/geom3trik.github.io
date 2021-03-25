---
layout: page
title: Receiving Events
category: Event System
order: 5
---
---


# Receiveing Events

Events are received by a widget through the `on_event()` function within the `EventHandler` trait which is implemented by all widgets. To access the message within an event, the message must be downcast to the correct type. For example, inside the `on_event` function:

```rs
if let Some(window_event) = event.message.downcast::<WindowEvent>() {
    // Do something with the window_event, like matching on the different variants
}
```