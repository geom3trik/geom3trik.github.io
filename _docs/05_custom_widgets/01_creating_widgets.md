---
layout: page
title: Creating Widgets
category: Custom Widgets
order: 1
---
---
Creating your own widgets in tuix is quite easy. There are just 4 steps.

## Step 1 - Defining the widget state struct

The first step in creating a widget is to define a struct for it. You can have data inside the struct but this data will be 'local data' which can only be accessed during building, event handling, and rendering of the widget.

```rs
pub struct MyAwesomeWidget {
    pub some_local_data: f32,
}
```

## Step 2 - Implement the widget struct

Techinally this step is optional, but if you've got data inside your widget then it's just good practice. Alternatively you could derive or implement `Default` for your widget.

```rs
impl MyAwesomeWidget {
    pub fn new() -> Self {
        Self {
          some_local_data: 42.0
        }
    }
}
```

## Step 3 - Implement the Widget trait

Implementing the `Widget` trait turns our custom struct into a widget that can be used in tuix. This trait has three methods:
 1. `on_build` - Called once when the widget is built and added into the tuix app.
 2. `on_event` - Called when an event is sent to the widget, or if the widget is on the propagation path of the event.
 3. `on_draw` - Called when a redraw of the ui occurs. This method is only required for custom drawing as most widgets will be drawn automatically based on their style properties.

`on_build()` is called when a widget is built for the first time. The purpose of this function is to allow for inline properties to be set and for composition of widgets. For example, our brand new widget could contain a `Button` widget that gets created when an instance of `MyAwesomeWidget` is built.

You might have noticed already that the return type of the `on_build` function is an associated type. This is because the entity that is returned is the one you have access to when you call the `build()` function on a widget. However, if a widget is composed of multiple things we might need access to more than one entity. An example of this might be a tab container which has an entity for containing the tabs and an entity for containing the content, and in this case we might change `Ret` to `(Entity, Entity)` so we can return both. In this case though, we will just return the single entity which corresponds to the instance of our new widget.

```rs
impl Widget for MyAwesomeWidget {
    type Ret = Entity;
    fn on_build(&mut self, state: &mut State, entity: Entity) -> Self::Ret {
        
        let some_button = Button::new().build(state, entity, |builder| builder);
        
        entity
    }

    ...
}
```


`on_event` is where all of the logic of the widget will go. This method allows the widget to respond to events which are sent to it. Tuix uses dynamic dispatch for events so you need to downcast the event message to the type you want to respond to. In this case our widget is going to respond to `WindowEvent` so we call the `event.message.downcast::<WindowEvent>()` to convert the event to the right type.

```rs

...
fn on_event(&mut self, state: &mut State, entity: Entity, event: &mut Event) -> bool {
    if let Some(window_event) = event.message.downcast::<WindowEvent>() {
        match window_event {
            // Do Stuff
        }
    }
    false
}
...
```

`on_draw` can be used to override how tuix will draw the widget. By default tuix will use the style properties to draw the widget, but if you want something more complicated this can be done using the `Canvas` provided by the `on_draw` method. For our custom widget we

```rs
impl EventHandler for MyAwesomeWidget {
    ...

    fn on_draw(&mut self, state: &mut State, entity: Entity, canvas: &mut Canvas) {

    }
}
```