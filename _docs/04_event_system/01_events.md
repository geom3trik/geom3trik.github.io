---
layout: page
title: Events
category: Event System
order: 1
---
---

# Event Description

An event is described by the Event struct:
```rs
#[derive(Clone, Debug)]
pub struct Event {
    // The entity that produced the event. Entity::null() for OS events or unspecified.
    pub origin: Entity,
    // The entity the event should be sent to. Entity::null() to send to all entities.
    pub target: Entity,
    // How the event propagates through the tree.
    pub propagation: Propagation,
    // Whether the event can be consumed
    pub consumable: bool,
    // Determines whether the event should continue to be propagated 
    pub(crate) consumed: bool,
    // Whether the event is unique (only the latest copy can exist in a queue at a time)
    pub unique: bool,
    // Specifies an order index which is used to sort the event queue
    pub order: i32,
    // The event message
    pub message: Box<dyn Message>,
}
```