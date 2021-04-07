---
layout: page
title: Important Concepts
category: Getting Started
order: 10
---
---
# Widgets
A widget is a rust type which implements the `Widget` trait. A widget can contain 'local' data which can be manipulated at build time, during event handling, and during the drawing phase. Each widget is given an `Entity` id when built into the app.

# Entities
An `Entity` is an id associated with each widget in your gui application. Under the hood an entity is an id which can be used to get and set various properties, such as style properties, which are stored in `State`.

# State
`State` represents the 'global' data of the elements in a gui application. For this reason, a mutable reference to state is passed around when building entities, handling events, and drawing.

# Hierarchy
Elements of a gui application are organised into a tree, where each element can have a single parent and multiple children. In tuix this tree is called the `Hierarchy`, and can be found in `State`. This hierarchy is used to propagate events as well as to draw the elements in the correct order.

