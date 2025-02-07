---
layout: page
title: Creating an App
category: Getting Started
order: 2
---
---

# A Basic Tuix App

The most basic tuix app looks like this:

```rs
use tuix::*;

fn main() {
    let mut app = Application::new(|state, window| {});

    app.run();
}
```

Currebtly the closure in `new()` is empty, but this is where we will build our application by adding widgets.

Running this code with `cargo run` will produce an empty gray window with a width of 800 pixels and a height of 600 pixels. This isn't very interesting, so in the next section we'll cover changing window properties like size, title and icon.

For now let's go over the two arguments provided by the closure:

 - `state` - This is a mutable reference to the UI `State`, which represents the 'global' data of the elements in a gui application, such as widget positions and style. A mutable reference to state is passed around when building widgets, handling events, and drawing widgets.

 - `window` - This is a mutable reference to a `WindowBuilder`. With this we can modify the window properties.

