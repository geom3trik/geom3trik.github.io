---
title: Pseudo-classes
category: Styling
order: 5
---
---

Pseudo-classes let you change the style of an element based on its state. There are 7 supported pseudo-classes in tuix:

- `:hover` - selects the top-most element under the mouse cursor
- `:over` - selects elements under the mouse cursor 
- `:active` - selects elements which have captured mouse events
- `:focus` - selects elements which have keyboard focus
- `:enabled` - selects elements which are enabled
- `:disabled` - selects elements which are disabled
- `:checked` - selects elements which are checked

## Setting Pseudo-classes on entities
Some pseudo-classes, such as hover, over, and focus, are set automatically by the application. However it's also possible to set pseudoclass properties on entities directly.

#### Enabled
```rs
entity.set_enabled(state, bool);
```

#### Disabled
```rs
entity.set_disabled(state, bool);
```

#### Active
```rs
entity.set_active(state, bool);
```

#### Checked
```rs
entity.set_checked(state, bool);
```