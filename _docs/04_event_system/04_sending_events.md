---
layout: page
title: Sending Events
category: Event System
order: 4
---
---

# Sending Events

Events are sent using the `state` like so:
```rs
state.insert_event(Event::new(CalculatorEvent::Digit('0')).target(entity));
```
This is from the `calculator.rs` example and shows how to send a custom event. 