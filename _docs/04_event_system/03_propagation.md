---
layout: page
title: Event Propagation
category: Event System
order: 3
---
---


# Event Propagation

It's worth taking a moment to understand how events propagate through tuix. Each application loop, sent events get put into a queue. On the next loop iteration, the events are flushed from the queue and sent to the corresponding targets one by one in the order of the hierarchy.

The hierarchy is a tree which contains all of the widgets in the application. The window is at the root of the tree and widgets and their children make up the branches and leaves. For example, an application with a window, a container, and a widget within the container would look like this in the hierarchy:

// Image here

There are four types of event propagation:

- `DownUp`: The event is sent from the root to the target and then back up to the root. This means that, unless the event is captured, many widgets along the path, except for the target, will receive the event twice.
- `Down`: The event propagates down from the root to the target.
- `Up`: The event propagates up from the target to the root.
- `Fall`: The event propagates from the target down the branch to the last leaf widget.
- `Direct`: The event is sent directly to the target and no other widgets.