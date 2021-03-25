---
layout: page
title: Extending Widgets
category: Custom Widgets
order: 2
---
---

As well as creating your own custom widgets, tuix allows for extending other widgets with additional data and functionality. There are 4 steps.

## Step 1 - Define the widget struct
Similar to creating your own widget, the first step is to define a widget struct. The main difference is that this widget struct will contain another widget. In this example we will extend the functionality of a `Button` by adding an `on_hover` event.
```rs
#[derive(Default)]
pub struct MyExtendedButton {
    pub button: Button,
    pub on_hover: Option<Event>,
}
```

## Step 2 - Implement the widget struct
If you are happy with the default values then you can skip this step. However, if you want to be able to set the local data of the contained button, this can be done here.
```rs
impl MyExtendedButton {
    pub fn new() -> Self {
        Self {
            button: Button::new(),
            on_hover: None,
        }
    }

    pub fn on_hover(self, event: Event) -> Self {
        self.on_hover = event;

        self
    }
}
```

## Step 3 - Implement the Widget trait
Inside the `on_build()` method of the `Widget` trait implementation we manually call the `on_build()` method of the contained button using the `entity` id. This causes the entity to become a button, effectively inheriting the buttons data. 
```rs
impl Widget for MyExtendedButton {
    type Ret = Entity;
        fn on_build(&mut self, state: &mut State, entity: Entity) -> Self::Ret {
        
        self.button.on_build(state, entity)
    }
}
```

Inside the `on_event()` method of the `Widget` trait implementation we manually call the `on_event` method of the contained button to 'inherit' the buttons' functionality. Now when a user clicks on an instance of `MyExtendedButton` the `on_press` event (if there is one) will be emitted. After this we extend the functionality by handling `WindowEvent::MouseOver` event to emit the contained `on_hover` event.
```rs
...
fn on_event(&mut self, state: &mut State, entity: Entity, event: &mut Event) -> bool {
    
    // Call on_event of contained button to 'inherit' button functionality
    self.button.on_event(state, entity, event);
    
    // Handle MouseOver event to emit the contained on_hover event
    if let Some(window_event) = event.message.downcast::<WindowEvent>() {
        match window_event {
            WindowEvent::MouseOver => {
                if event.target == entity {
                    if let Some(on_hover) = self.on_hover.clone() {
                        on_hover.origin = entity;
                        state.insert_event(on_hover);
                    }
                }
            }

            _=> {}
        }
    }
    false
}
...
```