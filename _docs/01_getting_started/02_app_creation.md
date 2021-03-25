---
layout: page
title: Creating an App
category: Getting Started
order: 2
---
---

The simplest tuix app looks like this:
```rs
use tuix::*;

fn main() {
    let mut app = Application::new(|win_desc, state, window| {
        win_desc
    });

    app.run();
}
```

