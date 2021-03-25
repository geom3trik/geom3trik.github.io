---
layout: page
title: Basic Tuix App
category: Getting Started
order: 2
---
---

A basic tuix app looks like this:

```rs
use tuix::*;

fn main() {
    let mut app = Application::new(|win_desc, state, window| {

        Button::with_label("Button!").build(state, window, |builder| {
            builder
                .set_width(Length::Pixels(100.0))
                .set_height(Length::Pixels(30.0))
                .set_background_color(Color::rgb(100,50,50))
        });

        win_desc.with_title("Hello GUI")
    });

    app.run();
}
```

This example will create a red 100 by 30 pixel button at the top left corner of a 800 by 600 pixel window, with label text "Button!". 